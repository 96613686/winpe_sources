# CXWizardPropertyBag::RemoveProperty(_GUID const *,ushort * const,void * * const,ulong * const)

- ea: `0x180026e60`
- end: `0x180026fee`
- name: `?RemoveProperty@CXWizardPropertyBag@@UEAAJPEBU_GUID@@QEAGQEAPEAXQEAK@Z`
- size: `398`
- prototype: `int(CXWizardPropertyBag *__hidden this, const struct _GUID *, unsigned __int16 *const, void **const, unsigned int *const)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008634`
- `0x18000ae04`
- `0x180026e60`
- `0x180032a02`
- `0x180032a30`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026f99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026f99`

## pseudocode

```c
__int64 __fastcall CXWizardPropertyBag::RemoveProperty(
        CXWizardPropertyBag *this,
        const struct _GUID *a2,
        unsigned __int16 *const a3,
        void **const a4,
        unsigned int *const a5)
{
  __int64 v10; // xmm0_8
  int v11; // eax
  __int64 v12; // r11
  unsigned int v13; // eax
  void *v14; // rcx
  unsigned int v15; // edi
  int v16; // [rsp+40h] [rbp-81h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-79h] BYREF
  unsigned int Data1; // [rsp+50h] [rbp-71h] BYREF
  __int64 v19; // [rsp+54h] [rbp-6Dh] BYREF
  int v20; // [rsp+5Ch] [rbp-65h]
  unsigned __int16 v21[56]; // [rsp+60h] [rbp-61h] BYREF

  pv = 0;
  v16 = 0;
  memset_0(&v19, 0, 0x74u);
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  if ( a3 )
  {
    if ( a2 )
    {
      v10 = *(_QWORD *)&a2->Data2;
      Data1 = a2->Data1;
      v11 = *(_DWORD *)&a2->Data4[4];
    }
    else
    {
      v10 = *(_QWORD *)((char *)this + 68);
      Data1 = *((_DWORD *)this + 16);
      v11 = *((_DWORD *)this + 19);
    }
    v20 = v11;
    v19 = v10;
    v21[0] = 0;
    StringCchCopyW(v21, 0x33u, a3);
    v13 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned int *, LPVOID *, int *, unsigned int *const, _QWORD))(**((_QWORD **)this + 10) + 56LL))(
            *((_QWORD *)this + 10),
            v12,
            &Data1,
            &pv,
            &v16,
            a5,
            0);
    v14 = pv;
    v15 = v13;
    if ( pv )
    {
      if ( a4 )
        *a4 = *(void **)pv;
      CoTaskMemFree(v14);
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_38def26b342f3b4a58e3bdaac3e43707_Traceguids, v15);
    return v15;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_38def26b342f3b4a58e3bdaac3e43707_Traceguids, 2147942487LL);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180026e60  push    rbp
0x180026e62  push    rbx
0x180026e63  push    rsi
0x180026e64  push    rdi
0x180026e65  push    r14
0x180026e67  push    r15
0x180026e69  lea     rbp, [rsp-27h]
0x180026e6e  sub     rsp, 0E8h
0x180026e75  mov     rax, cs:__security_cookie
0x180026e7c  xor     rax, rsp
0x180026e7f  mov     [rbp+4Fh+var_40], rax
0x180026e83  mov     rsi, [rbp+4Fh+arg_20]
0x180026e87  mov     rdi, rdx
0x180026e8a  xor     edx, edx; Val
0x180026e8c  mov     [rbp+4Fh+pv], 0
0x180026e94  mov     r15, r8
0x180026e97  mov     [rsp+110h+var_D0], 0
0x180026e9f  mov     r14, rcx
0x180026ea2  mov     rbx, r9
0x180026ea5  lea     rcx, [rbp+4Fh+var_BC]; void *
0x180026ea9  lea     r8d, [rdx+74h]; Size
0x180026ead  call    memset_0
0x180026eb2  test    rbx, rbx
0x180026eb5  jz      short loc_180026EBE
0x180026eb7  mov     qword ptr [rbx], 0
0x180026ebe  test    rsi, rsi
0x180026ec1  jz      short loc_180026EC9
0x180026ec3  mov     dword ptr [rsi], 0
0x180026ec9  test    r15, r15
0x180026ecc  jnz     short loc_180026F0B
0x180026ece  mov     rcx, cs:WPP_GLOBAL_Control
0x180026ed5  lea     rax, WPP_GLOBAL_Control
0x180026edc  cmp     rcx, rax
0x180026edf  jz      short loc_180026F01
0x180026ee1  test    byte ptr [rcx+1Ch], 8
0x180026ee5  jz      short loc_180026F01
0x180026ee7  mov     rcx, [rcx+10h]
0x180026eeb  lea     edx, [r15+15h]
0x180026eef  mov     r9d, 80070057h
0x180026ef5  lea     r8, WPP_38def26b342f3b4a58e3bdaac3e43707_Traceguids
0x180026efc  call    WPP_SF_d
0x180026f01  mov     eax, 80070057h
0x180026f06  jmp     loc_180026FD2
0x180026f0b  lea     r11, [r14+40h]
0x180026f0f  test    rdi, rdi
0x180026f12  jz      short loc_180026F23
0x180026f14  mov     eax, [rdi]
0x180026f16  movsd   xmm0, qword ptr [rdi+4]
0x180026f1b  mov     [rbp+4Fh+var_C0], eax
0x180026f1e  mov     eax, [rdi+0Ch]
0x180026f21  jmp     short loc_180026F33
0x180026f23  mov     eax, [r11]
0x180026f26  movsd   xmm0, qword ptr [r11+4]
0x180026f2c  mov     [rbp+4Fh+var_C0], eax
0x180026f2f  mov     eax, [r11+0Ch]
0x180026f33  mov     [rbp+4Fh+var_B4], eax
0x180026f36  lea     rcx, [rbp+4Fh+var_B0]; unsigned __int16 *
0x180026f3a  xor     eax, eax
0x180026f3c  movsd   [rbp+4Fh+var_BC], xmm0
0x180026f41  mov     r8, r15; unsigned __int16 *
0x180026f44  mov     [rbp+4Fh+var_B0], ax
0x180026f48  lea     edx, [rax+33h]; unsigned __int64
0x180026f4b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180026f50  mov     rcx, [r14+50h]
0x180026f54  lea     rdx, [rsp+110h+var_D0]
0x180026f59  mov     [rsp+110h+var_E0], 0
0x180026f62  lea     r9, [rbp+4Fh+pv]
0x180026f66  mov     [rsp+110h+var_E8], rsi
0x180026f6b  lea     r8, [rbp+4Fh+var_C0]
0x180026f6f  mov     [rsp+110h+var_F0], rdx
0x180026f74  mov     rdx, r11
0x180026f77  mov     rax, [rcx]
0x180026f7a  mov     rax, [rax+38h]
0x180026f7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f83  mov     rcx, [rbp+4Fh+pv]; pv
0x180026f87  mov     edi, eax
0x180026f89  test    rcx, rcx
0x180026f8c  jz      short loc_180026F9F
0x180026f8e  test    rbx, rbx
0x180026f91  jz      short loc_180026F99
0x180026f93  mov     rdx, [rcx]
0x180026f96  mov     [rbx], rdx
0x180026f99  call    cs:__imp_CoTaskMemFree
0x180026f9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180026fa6  lea     rax, WPP_GLOBAL_Control
0x180026fad  cmp     rcx, rax
0x180026fb0  jz      short loc_180026FD0
0x180026fb2  test    byte ptr [rcx+1Ch], 10h
0x180026fb6  jz      short loc_180026FD0
0x180026fb8  mov     rcx, [rcx+10h]
0x180026fbc  lea     r8, WPP_38def26b342f3b4a58e3bdaac3e43707_Traceguids
0x180026fc3  mov     edx, 16h
0x180026fc8  mov     r9d, edi
0x180026fcb  call    WPP_SF_d
0x180026fd0  mov     eax, edi
0x180026fd2  mov     rcx, [rbp+4Fh+var_40]
0x180026fd6  xor     rcx, rsp; StackCookie
0x180026fd9  call    __security_check_cookie
0x180026fde  add     rsp, 0E8h
0x180026fe5  pop     r15
0x180026fe7  pop     r14
0x180026fe9  pop     rdi
0x180026fea  pop     rsi
0x180026feb  pop     rbx
0x180026fec  pop     rbp
0x180026fed  retn
```
