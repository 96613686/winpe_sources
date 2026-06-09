# CXWizardPropertyBag::GetProperty(_GUID const *,ushort * const,void * * const,ulong * const)

- ea: `0x1800269a0`
- end: `0x180026b2e`
- name: `?GetProperty@CXWizardPropertyBag@@UEAAJPEBU_GUID@@QEAGQEAPEAXQEAK@Z`
- size: `398`
- prototype: `int(CXWizardPropertyBag *__hidden this, const struct _GUID *, unsigned __int16 *const, void **const, unsigned int *const)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008634`
- `0x18000ae04`
- `0x1800269a0`
- `0x180032a02`
- `0x180032a30`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026ad9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026ad9`

## pseudocode

```c
__int64 __fastcall CXWizardPropertyBag::GetProperty(
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
    v13 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned int *, LPVOID *, int *, unsigned int *const, _QWORD))(**((_QWORD **)this + 10) + 48LL))(
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_38def26b342f3b4a58e3bdaac3e43707_Traceguids, v15);
    return v15;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_38def26b342f3b4a58e3bdaac3e43707_Traceguids, 2147942487LL);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800269a0  push    rbp
0x1800269a2  push    rbx
0x1800269a3  push    rsi
0x1800269a4  push    rdi
0x1800269a5  push    r14
0x1800269a7  push    r15
0x1800269a9  lea     rbp, [rsp-27h]
0x1800269ae  sub     rsp, 0E8h
0x1800269b5  mov     rax, cs:__security_cookie
0x1800269bc  xor     rax, rsp
0x1800269bf  mov     [rbp+4Fh+var_40], rax
0x1800269c3  mov     rsi, [rbp+4Fh+arg_20]
0x1800269c7  mov     rdi, rdx
0x1800269ca  xor     edx, edx; Val
0x1800269cc  mov     [rbp+4Fh+pv], 0
0x1800269d4  mov     r15, r8
0x1800269d7  mov     [rsp+110h+var_D0], 0
0x1800269df  mov     r14, rcx
0x1800269e2  mov     rbx, r9
0x1800269e5  lea     rcx, [rbp+4Fh+var_BC]; void *
0x1800269e9  lea     r8d, [rdx+74h]; Size
0x1800269ed  call    memset_0
0x1800269f2  test    rbx, rbx
0x1800269f5  jz      short loc_1800269FE
0x1800269f7  mov     qword ptr [rbx], 0
0x1800269fe  test    rsi, rsi
0x180026a01  jz      short loc_180026A09
0x180026a03  mov     dword ptr [rsi], 0
0x180026a09  test    r15, r15
0x180026a0c  jnz     short loc_180026A4B
0x180026a0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180026a15  lea     rax, WPP_GLOBAL_Control
0x180026a1c  cmp     rcx, rax
0x180026a1f  jz      short loc_180026A41
0x180026a21  test    byte ptr [rcx+1Ch], 8
0x180026a25  jz      short loc_180026A41
0x180026a27  mov     rcx, [rcx+10h]
0x180026a2b  lea     edx, [r15+13h]
0x180026a2f  mov     r9d, 80070057h
0x180026a35  lea     r8, WPP_38def26b342f3b4a58e3bdaac3e43707_Traceguids
0x180026a3c  call    WPP_SF_d
0x180026a41  mov     eax, 80070057h
0x180026a46  jmp     loc_180026B12
0x180026a4b  lea     r11, [r14+40h]
0x180026a4f  test    rdi, rdi
0x180026a52  jz      short loc_180026A63
0x180026a54  mov     eax, [rdi]
0x180026a56  movsd   xmm0, qword ptr [rdi+4]
0x180026a5b  mov     [rbp+4Fh+var_C0], eax
0x180026a5e  mov     eax, [rdi+0Ch]
0x180026a61  jmp     short loc_180026A73
0x180026a63  mov     eax, [r11]
0x180026a66  movsd   xmm0, qword ptr [r11+4]
0x180026a6c  mov     [rbp+4Fh+var_C0], eax
0x180026a6f  mov     eax, [r11+0Ch]
0x180026a73  mov     [rbp+4Fh+var_B4], eax
0x180026a76  lea     rcx, [rbp+4Fh+var_B0]; unsigned __int16 *
0x180026a7a  xor     eax, eax
0x180026a7c  movsd   [rbp+4Fh+var_BC], xmm0
0x180026a81  mov     r8, r15; unsigned __int16 *
0x180026a84  mov     [rbp+4Fh+var_B0], ax
0x180026a88  lea     edx, [rax+33h]; unsigned __int64
0x180026a8b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180026a90  mov     rcx, [r14+50h]
0x180026a94  lea     rdx, [rsp+110h+var_D0]
0x180026a99  mov     [rsp+110h+var_E0], 0
0x180026aa2  lea     r9, [rbp+4Fh+pv]
0x180026aa6  mov     [rsp+110h+var_E8], rsi
0x180026aab  lea     r8, [rbp+4Fh+var_C0]
0x180026aaf  mov     [rsp+110h+var_F0], rdx
0x180026ab4  mov     rdx, r11
0x180026ab7  mov     rax, [rcx]
0x180026aba  mov     rax, [rax+30h]
0x180026abe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ac3  mov     rcx, [rbp+4Fh+pv]; pv
0x180026ac7  mov     edi, eax
0x180026ac9  test    rcx, rcx
0x180026acc  jz      short loc_180026ADF
0x180026ace  test    rbx, rbx
0x180026ad1  jz      short loc_180026AD9
0x180026ad3  mov     rdx, [rcx]
0x180026ad6  mov     [rbx], rdx
0x180026ad9  call    cs:__imp_CoTaskMemFree
0x180026adf  mov     rcx, cs:WPP_GLOBAL_Control
0x180026ae6  lea     rax, WPP_GLOBAL_Control
0x180026aed  cmp     rcx, rax
0x180026af0  jz      short loc_180026B10
0x180026af2  test    byte ptr [rcx+1Ch], 10h
0x180026af6  jz      short loc_180026B10
0x180026af8  mov     rcx, [rcx+10h]
0x180026afc  lea     r8, WPP_38def26b342f3b4a58e3bdaac3e43707_Traceguids
0x180026b03  mov     edx, 14h
0x180026b08  mov     r9d, edi
0x180026b0b  call    WPP_SF_d
0x180026b10  mov     eax, edi
0x180026b12  mov     rcx, [rbp+4Fh+var_40]
0x180026b16  xor     rcx, rsp; StackCookie
0x180026b19  call    __security_check_cookie
0x180026b1e  add     rsp, 0E8h
0x180026b25  pop     r15
0x180026b27  pop     r14
0x180026b29  pop     rdi
0x180026b2a  pop     rsi
0x180026b2b  pop     rbx
0x180026b2c  pop     rbp
0x180026b2d  retn
```
