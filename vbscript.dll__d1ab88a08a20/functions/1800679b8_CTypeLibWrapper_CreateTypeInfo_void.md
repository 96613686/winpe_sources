# CTypeLibWrapper::CreateTypeInfo(void)

- ea: `0x1800679b8`
- end: `0x180067bec`
- name: `?CreateTypeInfo@CTypeLibWrapper@@AEAAJXZ`
- size: `564`
- prototype: `__int64 __fastcall(CTypeLibWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180067cc0`

## callees

- `0x18001cb34`
- `0x18001eef0`
- `0x180043230`
- `0x1800679b8`
- `0x180079436`
- `0x180079490`
- `0x18007a010`

## import_xrefs

- `msvcrt!_ultow_s` at `0x180067a55`
- `msvcrt!_ultow_s` at `0x180067a55`

## pseudocode

```c
__int64 __fastcall CTypeLibWrapper::CreateTypeInfo(CTypeLibWrapper *this)
{
  int DispatchTypeInfo; // ebx
  unsigned int v4; // esi
  unsigned int v5; // r12d
  __int64 v6; // [rsp+30h] [rbp-49h] BYREF
  unsigned int v7; // [rsp+38h] [rbp-41h] BYREF
  struct ITypeInfo *v8; // [rsp+40h] [rbp-39h] BYREF
  _DWORD v9[8]; // [rsp+50h] [rbp-29h] BYREF
  __int16 v10; // [rsp+70h] [rbp-9h]
  __int16 v11; // [rsp+88h] [rbp+Fh]
  int v12; // [rsp+8Ch] [rbp+13h]
  wchar_t Buffer[12]; // [rsp+90h] [rbp+17h] BYREF

  v8 = 0;
  v6 = 0;
  if ( !(unsigned int)MUTX::Enter((CTypeLibWrapper *)((char *)this + 48)) )
    return 2147500037LL;
  if ( *((_QWORD *)this + 5) )
  {
    DispatchTypeInfo = 0;
  }
  else
  {
    DispatchTypeInfo = GetDispatchTypeInfo(&v8);
    if ( DispatchTypeInfo >= 0 )
    {
      memset(Buffer, 0, 22);
      _ultow_s(_InterlockedIncrement(&dword_180093828), Buffer, 0xBu, 10);
      DispatchTypeInfo = (*(__int64 (__fastcall **)(_QWORD, wchar_t *, __int64, __int64 *))(**((_QWORD **)this + 4)
                                                                                          + 24LL))(
                           *((_QWORD *)this + 4),
                           Buffer,
                           4,
                           &v6);
      if ( DispatchTypeInfo >= 0 )
      {
        v7 = 0;
        DispatchTypeInfo = (*(__int64 (__fastcall **)(__int64, struct ITypeInfo *, unsigned int *))(*(_QWORD *)v6 + 64LL))(
                             v6,
                             v8,
                             &v7);
        if ( DispatchTypeInfo >= 0 )
        {
          DispatchTypeInfo = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v6 + 80LL))(v6, 0, v7);
          if ( DispatchTypeInfo >= 0 )
          {
            memset_0(v9, 0, 0x40u);
            v12 = 3;
            v10 = 12;
            v4 = 0;
            v11 = 0;
            if ( *((_DWORD *)this + 3) )
            {
              while ( 1 )
              {
                v5 = v4 + 1;
                v9[0] = v4 + 1;
                DispatchTypeInfo = (*(__int64 (__fastcall **)(__int64, _QWORD, _DWORD *))(*(_QWORD *)v6 + 112LL))(
                                     v6,
                                     v4,
                                     v9);
                if ( DispatchTypeInfo < 0 )
                  break;
                DispatchTypeInfo = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v6 + 128LL))(
                                     v6,
                                     v4,
                                     *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 24LL) + 16LL * v4 + 8));
                if ( DispatchTypeInfo < 0 )
                  break;
                ++v4;
                if ( v5 >= *((_DWORD *)this + 3) )
                  goto LABEL_13;
              }
            }
            else
            {
LABEL_13:
              DispatchTypeInfo = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 200LL))(v6);
              if ( DispatchTypeInfo >= 0 )
                DispatchTypeInfo = (**(__int64 (__fastcall ***)(__int64, GUID *, char *))v6)(
                                     v6,
                                     &IID_ITypeInfo,
                                     (char *)this + 40);
            }
          }
        }
      }
    }
  }
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  if ( v8 )
    ((void (__fastcall *)(struct ITypeInfo *))v8->lpVtbl->Release)(v8);
  MUTX::Leave((CTypeLibWrapper *)((char *)this + 48));
  return (unsigned int)DispatchTypeInfo;
}

```

## disassembly

```asm
0x1800679b8  mov     [rsp-8+arg_8], rbx
0x1800679bd  mov     [rsp-8+arg_10], rsi
0x1800679c2  push    rbp
0x1800679c3  push    rdi
0x1800679c4  push    r12
0x1800679c6  push    r14
0x1800679c8  push    r15
0x1800679ca  lea     rbp, [rsp-37h]
0x1800679cf  sub     rsp, 0B0h
0x1800679d6  mov     rax, cs:__security_cookie
0x1800679dd  xor     rax, rsp
0x1800679e0  mov     [rbp+57h+var_28], rax
0x1800679e4  mov     rdi, rcx
0x1800679e7  mov     [rbp+57h+var_90], 0
0x1800679ef  add     rcx, 30h ; '0'; this
0x1800679f3  mov     [rbp+57h+var_A0], 0
0x1800679fb  call    ?Enter@MUTX@@QEAAHXZ; MUTX::Enter(void)
0x180067a00  test    eax, eax
0x180067a02  jnz     short loc_180067A0E
0x180067a04  mov     eax, 80004005h
0x180067a09  jmp     loc_180067BC3
0x180067a0e  cmp     qword ptr [rdi+28h], 0
0x180067a13  jz      short loc_180067A1C
0x180067a15  xor     ebx, ebx
0x180067a17  jmp     loc_180067B8E
0x180067a1c  lea     rcx, [rbp+57h+var_90]; struct ITypeInfo **
0x180067a20  call    ?GetDispatchTypeInfo@@YAJPEAPEAUITypeInfo@@@Z; GetDispatchTypeInfo(ITypeInfo * *)
0x180067a25  mov     ebx, eax
0x180067a27  test    eax, eax
0x180067a29  js      loc_180067B8E
0x180067a2f  xor     eax, eax
0x180067a31  xorps   xmm0, xmm0
0x180067a34  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x180067a38  mov     qword ptr [rbp+57h+Buffer+0Eh], rax
0x180067a3c  lea     ecx, [rax+1]
0x180067a3f  lock xadd cs:dword_180093828, ecx
0x180067a47  inc     ecx; Value
0x180067a49  lea     r9d, [rax+0Ah]; Radix
0x180067a4d  lea     r8d, [rax+0Bh]; BufferCount
0x180067a51  lea     rdx, [rbp+57h+Buffer]; Buffer
0x180067a55  call    cs:__imp__ultow_s
0x180067a5c  nop     dword ptr [rax+rax+00h]
0x180067a61  mov     rcx, [rdi+20h]
0x180067a65  lea     r9, [rbp+57h+var_A0]
0x180067a69  mov     r8d, 4
0x180067a6f  lea     rdx, [rbp+57h+Buffer]
0x180067a73  mov     rax, [rcx]
0x180067a76  mov     rax, [rax+18h]
0x180067a7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067a7f  mov     ebx, eax
0x180067a81  test    eax, eax
0x180067a83  js      loc_180067B8E
0x180067a89  mov     rcx, [rbp+57h+var_A0]
0x180067a8d  lea     r8, [rbp+57h+var_98]
0x180067a91  mov     rdx, [rbp+57h+var_90]
0x180067a95  mov     [rbp+57h+var_98], 0
0x180067a9c  mov     rax, [rcx]
0x180067a9f  mov     rax, [rax+40h]
0x180067aa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067aa8  mov     ebx, eax
0x180067aaa  test    eax, eax
0x180067aac  js      loc_180067B8E
0x180067ab2  mov     rcx, [rbp+57h+var_A0]
0x180067ab6  xor     edx, edx
0x180067ab8  mov     r8d, [rbp+57h+var_98]
0x180067abc  mov     rax, [rcx]
0x180067abf  mov     rax, [rax+50h]
0x180067ac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067ac8  mov     ebx, eax
0x180067aca  test    eax, eax
0x180067acc  js      loc_180067B8E
0x180067ad2  xor     edx, edx; Val
0x180067ad4  lea     rcx, [rbp+57h+var_80]; void *
0x180067ad8  lea     r8d, [rdx+40h]; Size
0x180067adc  call    memset_0
0x180067ae1  mov     eax, 0Ch
0x180067ae6  mov     [rbp+57h+var_44], 3
0x180067aed  mov     [rbp+57h+var_60], ax
0x180067af1  xor     esi, esi
0x180067af3  xor     eax, eax
0x180067af5  mov     [rbp+57h+var_48], ax
0x180067af9  cmp     [rdi+0Ch], eax
0x180067afc  jbe     short loc_180067B59
0x180067afe  mov     rcx, [rbp+57h+var_A0]
0x180067b02  lea     r12d, [rsi+1]
0x180067b06  mov     [rbp+57h+var_80], r12d
0x180067b0a  lea     r8, [rbp+57h+var_80]
0x180067b0e  mov     edx, esi
0x180067b10  mov     rax, [rcx]
0x180067b13  mov     rax, [rax+70h]
0x180067b17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067b1c  mov     ebx, eax
0x180067b1e  test    eax, eax
0x180067b20  js      short loc_180067B8E
0x180067b22  mov     rax, [rdi+10h]
0x180067b26  mov     edx, esi
0x180067b28  mov     rcx, [rbp+57h+var_A0]
0x180067b2c  mov     r10d, esi
0x180067b2f  add     r10, r10
0x180067b32  mov     r8, [rax+18h]
0x180067b36  mov     r9, [rcx]
0x180067b39  mov     r8, [r8+r10*8+8]
0x180067b3e  mov     rax, [r9+80h]
0x180067b45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067b4a  mov     ebx, eax
0x180067b4c  test    eax, eax
0x180067b4e  js      short loc_180067B8E
0x180067b50  mov     esi, r12d
0x180067b53  cmp     r12d, [rdi+0Ch]
0x180067b57  jb      short loc_180067AFE
0x180067b59  mov     rcx, [rbp+57h+var_A0]
0x180067b5d  mov     rax, [rcx]
0x180067b60  mov     rax, [rax+0C8h]
0x180067b67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067b6c  mov     ebx, eax
0x180067b6e  test    eax, eax
0x180067b70  js      short loc_180067B8E
0x180067b72  mov     rcx, [rbp+57h+var_A0]
0x180067b76  lea     r8, [rdi+28h]
0x180067b7a  lea     rdx, IID_ITypeInfo
0x180067b81  mov     rax, [rcx]
0x180067b84  mov     rax, [rax]
0x180067b87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067b8c  mov     ebx, eax
0x180067b8e  mov     rcx, [rbp+57h+var_A0]
0x180067b92  test    rcx, rcx
0x180067b95  jz      short loc_180067BA3
0x180067b97  mov     rax, [rcx]
0x180067b9a  mov     rax, [rax+10h]
0x180067b9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067ba3  mov     rcx, [rbp+57h+var_90]
0x180067ba7  test    rcx, rcx
0x180067baa  jz      short loc_180067BB8
0x180067bac  mov     rax, [rcx]
0x180067baf  mov     rax, [rax+10h]
0x180067bb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067bb8  lea     rcx, [rdi+30h]; this
0x180067bbc  call    ?Leave@MUTX@@QEAAXXZ; MUTX::Leave(void)
0x180067bc1  mov     eax, ebx
0x180067bc3  mov     rcx, [rbp+57h+var_28]
0x180067bc7  xor     rcx, rsp; StackCookie
0x180067bca  call    __security_check_cookie
0x180067bcf  lea     r11, [rsp+0D0h+var_20]
0x180067bd7  mov     rbx, [r11+38h]
0x180067bdb  mov     rsi, [r11+40h]
0x180067bdf  mov     rsp, r11
0x180067be2  pop     r15
0x180067be4  pop     r14
0x180067be6  pop     r12
0x180067be8  pop     rdi
0x180067be9  pop     rbp
0x180067bea  retn
```
