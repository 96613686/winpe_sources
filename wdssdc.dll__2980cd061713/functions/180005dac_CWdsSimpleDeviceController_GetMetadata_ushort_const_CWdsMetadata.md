# CWdsSimpleDeviceController::GetMetadata(ushort const *,CWdsMetadata *)

- ea: `0x180005dac`
- end: `0x180005eea`
- name: `?GetMetadata@CWdsSimpleDeviceController@@QEAAKPEBGPEAVCWdsMetadata@@@Z`
- size: `318`
- prototype: `__int64 __fastcall(CWdsSimpleDeviceController *this, const unsigned __int16 *, struct CWdsMetadata *)`
- caller_count: `6`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800055b0`
- `0x180005b10`
- `0x180005c80`
- `0x180006598`
- `0x1800068d0`
- `0x180007214`

## callees

- `0x1800015d4`
- `0x180001934`
- `0x180005508`
- `0x180005dac`
- `0x180006dd8`
- `0x180009194`

## import_xrefs

- `KERNEL32!GetPrivateProfileSectionW` at `0x180005e44`
- `KERNEL32!GetPrivateProfileSectionW` at `0x180005e44`
- `KERNEL32!EnterCriticalSection` at `0x180005dd9`
- `KERNEL32!EnterCriticalSection` at `0x180005dd9`

## pseudocode

```c
__int64 __fastcall CWdsSimpleDeviceController::GetMetadata(
        CWdsSimpleDeviceController *this,
        const unsigned __int16 *a2,
        struct CWdsMetadata *a3)
{
  WCHAR *v6; // rbx
  DWORD v7; // esi
  unsigned int v8; // edi
  unsigned __int64 v9; // rax
  WCHAR *v10; // rax
  __int64 v11; // rdx
  DWORD PrivateProfileSectionW; // ecx
  __int64 v13; // r8
  const unsigned __int16 *v14; // rdi
  unsigned int i; // esi
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rax
  char *v20; // [rsp+20h] [rbp-38h] BYREF
  int v21; // [rsp+28h] [rbp-30h]

  v20 = (char *)this + 72;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v21 = 1;
  v6 = 0;
  v7 = 512;
  v8 = 2;
  do
  {
    v7 *= 2;
    if ( v6 )
      operator delete(v6);
    v9 = 2LL * v7;
    if ( !is_mul_ok(v7, 2u) )
      v9 = -1;
    v10 = (WCHAR *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
    v6 = v10;
    if ( !v10 )
    {
      v8 = 8;
      goto LABEL_17;
    }
    PrivateProfileSectionW = GetPrivateProfileSectionW(a2, v10, v7, *((LPCWSTR *)this + 14));
  }
  while ( PrivateProfileSectionW == v7 - 2 );
  if ( PrivateProfileSectionW )
  {
    v14 = v6;
    for ( i = 0; *v14; v14 += v18 + 1 )
    {
      i = CWdsMetadata::AppendEntry(a3, v14);
      if ( (unsigned int)ElValidateWin32(i, v16, v17, 320) )
        break;
      v18 = -1;
      do
        ++v18;
      while ( v14[v18] );
    }
    v8 = i;
    ElValidateWin32(i, v11, v13, 386);
  }
  operator delete(v6);
LABEL_17:
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(&v20);
  return v8;
}

```

## disassembly

```asm
0x180005dac  mov     rax, rsp
0x180005daf  mov     [rax+8], rbx
0x180005db3  mov     [rax+10h], rbp
0x180005db7  mov     [rax+18h], rsi
0x180005dbb  push    rdi
0x180005dbc  push    r12
0x180005dbe  push    r13
0x180005dc0  push    r14
0x180005dc2  push    r15
0x180005dc4  sub     rsp, 30h
0x180005dc8  mov     rbp, rcx
0x180005dcb  mov     r15, r8
0x180005dce  add     rcx, 48h ; 'H'; lpCriticalSection
0x180005dd2  mov     r14, rdx
0x180005dd5  mov     [rax-38h], rcx
0x180005dd9  call    cs:__imp_EnterCriticalSection
0x180005de0  nop     dword ptr [rax+rax+00h]
0x180005de5  xor     r12d, r12d
0x180005de8  mov     [rsp+58h+var_30], 1
0x180005df0  mov     ebx, r12d
0x180005df3  mov     esi, 200h
0x180005df8  or      r13, 0FFFFFFFFFFFFFFFFh
0x180005dfc  lea     edi, [r12+2]
0x180005e01  add     esi, esi
0x180005e03  test    rbx, rbx
0x180005e06  jz      short loc_180005E10
0x180005e08  mov     rcx, rbx; Block
0x180005e0b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005e10  mov     ecx, esi
0x180005e12  mov     rax, rdi
0x180005e15  mul     rcx
0x180005e18  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005e1f  cmovb   rax, r13
0x180005e23  mov     rcx, rax; unsigned __int64
0x180005e26  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180005e2b  mov     rbx, rax
0x180005e2e  test    rax, rax
0x180005e31  jz      loc_180005EBB
0x180005e37  mov     r9, [rbp+70h]; lpFileName
0x180005e3b  mov     r8d, esi; nSize
0x180005e3e  mov     rdx, rax; lpReturnedString
0x180005e41  mov     rcx, r14; lpAppName
0x180005e44  call    cs:__imp_GetPrivateProfileSectionW
0x180005e4b  nop     dword ptr [rax+rax+00h]
0x180005e50  mov     ecx, eax
0x180005e52  lea     eax, [rsi-2]
0x180005e55  cmp     ecx, eax
0x180005e57  jz      short loc_180005E01
0x180005e59  test    ecx, ecx
0x180005e5b  jz      short loc_180005EB1
0x180005e5d  mov     rdi, rbx
0x180005e60  mov     esi, r12d
0x180005e63  cmp     [rbx], r12w
0x180005e67  jz      short loc_180005EA2
0x180005e69  mov     rdx, rdi; unsigned __int16 *
0x180005e6c  mov     rcx, r15; this
0x180005e6f  call    ?AppendEntry@CWdsMetadata@@QEAAKPEBG@Z; CWdsMetadata::AppendEntry(ushort const *)
0x180005e74  mov     r9d, 140h
0x180005e7a  mov     ecx, eax
0x180005e7c  mov     esi, eax
0x180005e7e  call    ElValidateWin32
0x180005e83  test    eax, eax
0x180005e85  jnz     short loc_180005EA2
0x180005e87  mov     rax, r13
0x180005e8a  inc     rax
0x180005e8d  cmp     [rdi+rax*2], r12w
0x180005e92  jnz     short loc_180005E8A
0x180005e94  lea     rdi, [rdi+rax*2]
0x180005e98  add     rdi, 2
0x180005e9c  cmp     [rdi], r12w
0x180005ea0  jnz     short loc_180005E69
0x180005ea2  mov     r9d, 182h
0x180005ea8  mov     ecx, esi
0x180005eaa  mov     edi, esi
0x180005eac  call    ElValidateWin32
0x180005eb1  mov     rcx, rbx; Block
0x180005eb4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005eb9  jmp     short loc_180005EC0
0x180005ebb  mov     edi, 8
0x180005ec0  lea     rcx, [rsp+58h+var_38]
0x180005ec5  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x180005eca  mov     rbx, [rsp+58h+arg_0]
0x180005ecf  mov     eax, edi
0x180005ed1  mov     rbp, [rsp+58h+arg_8]
0x180005ed6  mov     rsi, [rsp+58h+arg_10]
0x180005edb  add     rsp, 30h
0x180005edf  pop     r15
0x180005ee1  pop     r14
0x180005ee3  pop     r13
0x180005ee5  pop     r12
0x180005ee7  pop     rdi
0x180005ee8  retn
```
