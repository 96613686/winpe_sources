# SkmiCreateSectionForHotpatch

- ea: `0x140047ac8`
- end: `0x140047bed`
- name: `SkmiCreateSectionForHotpatch`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140048b08`

## callees

- `0x140002ef0`
- `0x14000e130`
- `0x140047ac8`
- `0x1400a0df8`
- `0x1400ee8b0`
- `0x1400eff90`
- `0x1400f3620`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiCreateSectionForHotpatch(_QWORD *a1, unsigned int a2, unsigned int a3, int a4, __int64 a5)
{
  int Handle; // edi
  __int64 v10; // rbx
  int v11; // eax
  __int64 v12; // rsi
  __int64 v14; // [rsp+30h] [rbp-71h] BYREF
  __int64 v15; // [rsp+38h] [rbp-69h] BYREF
  unsigned int v16; // [rsp+40h] [rbp-61h] BYREF
  __int64 v17; // [rsp+48h] [rbp-59h]
  unsigned __int64 v18; // [rsp+50h] [rbp-51h]
  unsigned __int64 v19; // [rsp+58h] [rbp-49h]

  v15 = 0;
  v14 = 0;
  memset_0(&v16, 0, 0x68u);
  LODWORD(v19) = a4;
  HIWORD(v16) = 55;
  v17 = a5;
  v18 = __PAIR64__(a3, a2);
  BYTE4(v19) = *((_BYTE *)KeGetPcr()->NtTib.StackBase + 96);
  SkCallNormalMode(&v16);
  Handle = v17;
  if ( (int)v17 >= 0 )
  {
    v10 = v18;
    v11 = SkobReferenceObjectByHandle(v19, 0, 1, (__int64)&SkmiImageType, &v14, 0);
    v12 = v14;
    Handle = v11;
    if ( v11 >= 0 )
    {
      Handle = SkobCreateHandle(v14, 0, v10, (__int64)&v15);
      if ( Handle >= 0 )
      {
        v10 = 0;
        *a1 = v15;
      }
    }
    if ( v12 )
      SkobDereferenceObject(v12);
    if ( v10 )
      NkClose(v10);
  }
  return (unsigned int)Handle;
}

```

## disassembly

```asm
0x140047ac8  push    rbp
0x140047aca  push    rbx
0x140047acb  push    rsi
0x140047acc  push    rdi
0x140047acd  push    r12
0x140047acf  push    r14
0x140047ad1  push    r15
0x140047ad3  lea     rbp, [rsp-1Fh]
0x140047ad8  sub     rsp, 0C0h
0x140047adf  mov     rax, cs:__security_cookie
0x140047ae6  xor     rax, rsp
0x140047ae9  mov     [rbp+4Fh+var_40], rax
0x140047aed  mov     rdi, [rbp+4Fh+arg_20]
0x140047af1  mov     r14d, edx
0x140047af4  xor     edx, edx; Val
0x140047af6  mov     [rbp+4Fh+var_B8], 0
0x140047afe  mov     r15d, r8d
0x140047b01  mov     [rbp+4Fh+var_C0], 0
0x140047b09  mov     r12, rcx
0x140047b0c  mov     rbx, rdi
0x140047b0f  lea     rcx, [rbp+4Fh+var_B0]; void *
0x140047b13  sar     rbx, 20h
0x140047b17  lea     r8d, [rdx+68h]; Size
0x140047b1b  mov     esi, r9d
0x140047b1e  call    memset_0
0x140047b23  mov     dword ptr [rbp+4Fh+var_98], esi
0x140047b26  mov     eax, 37h ; '7'
0x140047b2b  mov     [rbp+4Fh+var_AE], ax
0x140047b2f  mov     dword ptr [rbp+4Fh+var_A8], edi
0x140047b32  mov     dword ptr [rbp+4Fh+var_A8+4], ebx
0x140047b35  mov     dword ptr [rbp+4Fh+var_A0], r14d
0x140047b39  mov     dword ptr [rbp+4Fh+var_A0+4], r15d
0x140047b3d  mov     rax, gs:8
0x140047b46  mov     cl, [rax+60h]
0x140047b49  mov     byte ptr [rbp+4Fh+var_98+4], cl
0x140047b4c  lea     rcx, [rbp+4Fh+var_B0]
0x140047b50  call    SkCallNormalMode
0x140047b55  mov     edi, dword ptr [rbp+4Fh+var_A8]
0x140047b58  test    edi, edi
0x140047b5a  js      short loc_140047BCC
0x140047b5c  mov     rcx, [rbp+4Fh+var_98]
0x140047b60  lea     rax, [rbp+4Fh+var_C0]
0x140047b64  mov     rbx, [rbp+4Fh+var_A0]
0x140047b68  lea     r9, SkmiImageType
0x140047b6f  mov     [rsp+0F0h+var_C8], 0
0x140047b78  mov     r8b, 1
0x140047b7b  xor     edx, edx
0x140047b7d  mov     [rsp+0F0h+var_D0], rax
0x140047b82  call    SkobReferenceObjectByHandle
0x140047b87  mov     rsi, [rbp+4Fh+var_C0]
0x140047b8b  mov     edi, eax
0x140047b8d  test    eax, eax
0x140047b8f  js      short loc_140047BB2
0x140047b91  lea     r9, [rbp+4Fh+var_B8]
0x140047b95  mov     r8, rbx
0x140047b98  xor     edx, edx
0x140047b9a  mov     rcx, rsi
0x140047b9d  call    SkobCreateHandle
0x140047ba2  mov     edi, eax
0x140047ba4  test    eax, eax
0x140047ba6  js      short loc_140047BB2
0x140047ba8  mov     rax, [rbp+4Fh+var_B8]
0x140047bac  xor     ebx, ebx
0x140047bae  mov     [r12], rax
0x140047bb2  test    rsi, rsi
0x140047bb5  jz      short loc_140047BBF
0x140047bb7  mov     rcx, rsi
0x140047bba  call    SkobDereferenceObject
0x140047bbf  test    rbx, rbx
0x140047bc2  jz      short loc_140047BCC
0x140047bc4  mov     rcx, rbx
0x140047bc7  call    NkClose
0x140047bcc  mov     eax, edi
0x140047bce  mov     rcx, [rbp+4Fh+var_40]
0x140047bd2  xor     rcx, rsp; StackCookie
0x140047bd5  call    __security_check_cookie
0x140047bda  add     rsp, 0C0h
0x140047be1  pop     r15
0x140047be3  pop     r14
0x140047be5  pop     r12
0x140047be7  pop     rdi
0x140047be8  pop     rsi
0x140047be9  pop     rbx
0x140047bea  pop     rbp
0x140047beb  retn
```
