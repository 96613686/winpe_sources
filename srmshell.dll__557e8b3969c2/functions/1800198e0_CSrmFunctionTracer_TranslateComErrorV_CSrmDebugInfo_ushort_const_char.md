# CSrmFunctionTracer::TranslateComErrorV(CSrmDebugInfo,ushort const *,char *)

- ea: `0x1800198e0`
- end: `0x180019b7d`
- name: `?TranslateComErrorV@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGPEAD@Z`
- size: `669`
- prototype: `void __fastcall __noreturn(CSrmFunctionTracerBase *, const struct CSrmDebugInfo *, wchar_t *, va_list)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180019850`

## callees

- `0x1800019e4`
- `0x180001e44`
- `0x1800054c0`
- `0x180016170`
- `0x180016518`
- `0x1800166ec`
- `0x180016830`
- `0x1800180a0`
- `0x180018ea8`
- `0x1800191ec`
- `0x1800198e0`
- `0x180020010`

## import_xrefs

- `OLEAUT32!__imp_GetErrorInfo` at `0x1800199c6`
- `OLEAUT32!__imp_GetErrorInfo` at `0x1800199c6`

## pseudocode

```c
void __fastcall __noreturn CSrmFunctionTracer::TranslateComErrorV(
        CSrmFunctionTracerBase *a1,
        const struct CSrmDebugInfo *a2,
        wchar_t *a3,
        va_list a4)
{
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rbx
  unsigned __int16 *v10; // rcx
  DWORD v11; // ebx
  __int16 *v12; // rdi
  __int16 *Buffer; // r15
  const struct CSrmDebugInfo *v14; // rax
  struct CSrmDebugInfo *v15; // rax
  struct CSrmDebugInfo *v16; // rax
  CSrmDebugInfo *v17; // rax
  const struct CSrmDebugInfo *v18; // rax
  const struct CSrmDebugInfo *v19; // rax
  __int64 v20; // r9
  unsigned int v21; // [rsp+20h] [rbp-E0h]
  va_list Args; // [rsp+30h] [rbp-D0h]
  _BYTE *pExceptionObject; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v24; // [rsp+48h] [rbp-B8h] BYREF
  IErrorInfo *pperrinfo; // [rsp+50h] [rbp-B0h] BYREF
  __int16 *v26; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v27; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v28[144]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v29[144]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v30[200]; // [rsp+188h] [rbp+88h] BYREF

  v8 = (unsigned __int16 *)operator new[](0x3EAu, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  v27 = v8;
  if ( !v8 )
  {
    LODWORD(pExceptionObject) = -2147024882;
    throw (long *)&pExceptionObject;
  }
  pExceptionObject = 0;
  v24 = 0;
  StringCchVPrintfExW(v8, 0x1F4u, &v24, (unsigned __int64 *)&pExceptionObject, v21, a3, a4);
  if ( pExceptionObject == (_BYTE *)1 )
  {
    v10 = v24;
    if ( (__int64)(((char *)v24 - (char *)v9) & 0xFFFFFFFFFFFFFFFEuLL) > 6 )
    {
      *((_DWORD *)v24 - 1) = 3014702;
      *(v10 - 3) = 46;
    }
  }
  v11 = *((_DWORD *)a1 + 2);
  if ( !v11 )
    v11 = -2147418113;
  pperrinfo = 0;
  v26 = 0;
  if ( GetErrorInfo(0, &pperrinfo) >= 0 && pperrinfo )
    ((void (__fastcall *)(IErrorInfo *, __int16 **))pperrinfo->lpVtbl->GetDescription)(pperrinfo, &v26);
  v12 = (__int16 *)&qword_180023088;
  if ( v26 )
    v12 = v26;
  if ( v11 != -2147024882
    && v11 != -2147024888
    && v11 != -2147024783
    && v11 != -2147023877
    && v11 != -2147023446
    && v11 != -2147023738 )
  {
    Buffer = (__int16 *)CSrmOutputBuffer::GetBuffer((CSrmOutputBuffer *)&v27);
    v24 = (unsigned __int16 *)v29;
    if ( v11 == -2147024784 )
    {
      v14 = CSrmDebugInfo::CSrmDebugInfo((CSrmDebugInfo *)v29, a2);
      CSrmFunctionTracer::Throw(a1, v14, -2147200236, L"Insufficient disk space detected. %s - %s", Buffer, v12);
    }
    v15 = CSrmDebugInfo::operator<<(a2, (CSrmDebugInfo *)v28, Buffer);
    v16 = CSrmDebugInfo::operator<<(v15, (CSrmDebugInfo *)v30, v12);
    v17 = CSrmDebugInfo::operator<<(v16, (CSrmDebugInfo *)v29, v11);
    CSrmFunctionTracer::LogError((__int64)a1, 0x80042009, (__int64)v17, 1u);
    CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)v30);
    CSrmDebugInfo::~CSrmDebugInfo((CSrmDebugInfo *)v28);
    pExceptionObject = v28;
    v18 = CSrmDebugInfo::CSrmDebugInfo((CSrmDebugInfo *)v28, a2);
    LODWORD(Args) = v11;
    CSrmFunctionTracer::Throw(a1, v18, -2147200234, L"Unexpected error: %s - %s [hr = 0x%08lx]", Buffer, v12, Args);
  }
  CSrmOutputBuffer::GetBuffer((CSrmOutputBuffer *)&v27);
  v24 = (unsigned __int16 *)v28;
  v19 = CSrmDebugInfo::CSrmDebugInfo((CSrmDebugInfo *)v28, a2);
  CSrmFunctionTracer::Throw(a1, v19, -2147024882, L"Out of memory detected. %s - %s", v20, v12);
}

```

## disassembly

```asm
0x1800198e0  mov     [rsp-8+arg_8], rdx
0x1800198e5  push    rbp
0x1800198e6  push    rbx
0x1800198e7  push    rsi
0x1800198e8  push    rdi
0x1800198e9  push    r14
0x1800198eb  push    r15
0x1800198ed  lea     rbp, [rsp-128h]
0x1800198f5  sub     rsp, 228h
0x1800198fc  mov     rdi, r9
0x1800198ff  mov     r15, r8
0x180019902  mov     r14, rdx
0x180019905  mov     rsi, rcx
0x180019908  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001990f  mov     ecx, 3EAh; unsigned __int64
0x180019914  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180019919  mov     rbx, rax
0x18001991c  mov     [rsp+250h+var_1F0], rax
0x180019921  test    rax, rax
0x180019924  jnz     short loc_180019940
0x180019926  mov     dword ptr [rsp+250h+pExceptionObject], 8007000Eh
0x18001992e  lea     rdx, _TI1J; pThrowInfo
0x180019935  lea     rcx, [rsp+250h+pExceptionObject]; pExceptionObject
0x18001993a  call    _CxxThrowException_0
0x180019940  mov     [rsp+250h+pExceptionObject], 0
0x180019949  mov     [rsp+250h+var_208], 0
0x180019952  mov     [rsp+250h+Args], rdi; Args
0x180019957  mov     [rsp+250h+Format], r15; Format
0x18001995c  lea     r9, [rsp+250h+pExceptionObject]; unsigned __int64 *
0x180019961  lea     r8, [rsp+250h+var_208]; unsigned __int16 **
0x180019966  mov     edx, 1F4h; unsigned __int64
0x18001996b  mov     rcx, rbx; unsigned __int16 *
0x18001996e  call    ?StringCchVPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGPEAD@Z; StringCchVPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,char *)
0x180019973  cmp     [rsp+250h+pExceptionObject], 1
0x180019979  jnz     short loc_1800199A0
0x18001997b  mov     rcx, [rsp+250h+var_208]
0x180019980  mov     rax, rcx
0x180019983  sub     rax, rbx
0x180019986  and     rax, 0FFFFFFFFFFFFFFFEh
0x18001998a  cmp     rax, 6
0x18001998e  jle     short loc_1800199A0
0x180019990  mov     eax, 2Eh ; '.'
0x180019995  mov     dword ptr [rcx-4], 2E002Eh
0x18001999c  mov     [rcx-6], ax
0x1800199a0  mov     ebx, [rsi+8]
0x1800199a3  mov     eax, 8000FFFFh
0x1800199a8  test    ebx, ebx
0x1800199aa  cmovz   ebx, eax
0x1800199ad  mov     [rsp+250h+pperrinfo], 0
0x1800199b6  mov     [rsp+250h+var_1F8], 0
0x1800199bf  lea     rdx, [rsp+250h+pperrinfo]; pperrinfo
0x1800199c4  xor     ecx, ecx; dwReserved
0x1800199c6  call    cs:__imp_GetErrorInfo
0x1800199cc  test    eax, eax
0x1800199ce  js      short loc_1800199EB
0x1800199d0  mov     rcx, [rsp+250h+pperrinfo]
0x1800199d5  test    rcx, rcx
0x1800199d8  jz      short loc_1800199EB
0x1800199da  mov     rax, [rcx]
0x1800199dd  lea     rdx, [rsp+250h+var_1F8]
0x1800199e2  mov     rax, [rax+28h]
0x1800199e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199eb  mov     rax, [rsp+250h+var_1F8]
0x1800199f0  lea     rdi, qword_180023088
0x1800199f7  test    rax, rax
0x1800199fa  cmovnz  rdi, rax
0x1800199fe  cmp     ebx, 8007000Eh
0x180019a04  jz      loc_180019B35
0x180019a0a  cmp     ebx, 80070008h
0x180019a10  jz      loc_180019B35
0x180019a16  cmp     ebx, 80070071h
0x180019a1c  jz      loc_180019B35
0x180019a22  cmp     ebx, 800703FBh
0x180019a28  jz      loc_180019B35
0x180019a2e  cmp     ebx, 800705AAh
0x180019a34  jz      loc_180019B35
0x180019a3a  cmp     ebx, 80070486h
0x180019a40  jz      loc_180019B35
0x180019a46  lea     rcx, [rsp+250h+var_1F0]; this
0x180019a4b  call    ?GetBuffer@CSrmOutputBuffer@@QEAAPEAGXZ; CSrmOutputBuffer::GetBuffer(void)
0x180019a50  mov     r15, rax
0x180019a53  lea     rax, [rbp+150h+var_158]
0x180019a57  mov     [rsp+250h+var_208], rax
0x180019a5c  cmp     ebx, 80070070h
0x180019a62  jnz     short loc_180019A94
0x180019a64  mov     rdx, r14; struct CSrmDebugInfo *
0x180019a67  lea     rcx, [rbp+150h+var_158]; this
0x180019a6b  call    ??0CSrmDebugInfo@@QEAA@AEBU0@@Z; CSrmDebugInfo::CSrmDebugInfo(CSrmDebugInfo const &)
0x180019a70  nop
0x180019a71  mov     [rsp+250h+Format], rdi
0x180019a76  mov     [rsp+250h+var_230], r15
0x180019a7b  lea     r9, aInsufficientDi_0; "Insufficient disk space detected. %s - "...
0x180019a82  mov     r8d, 80045314h
0x180019a88  mov     rdx, rax
0x180019a8b  mov     rcx, rsi
0x180019a8e  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x180019a94  mov     r8, r15
0x180019a97  lea     rdx, [rsp+250h+var_1E8]; this
0x180019a9c  mov     rcx, r14; struct CSrmDebugInfo *
0x180019a9f  call    ??6CSrmDebugInfo@@QEAA?AU0@PEBG@Z; CSrmDebugInfo::operator<<(ushort const *)
0x180019aa4  nop
0x180019aa5  mov     r8, rdi
0x180019aa8  lea     rdx, [rbp+150h+var_C8]; this
0x180019aaf  mov     rcx, rax; struct CSrmDebugInfo *
0x180019ab2  call    ??6CSrmDebugInfo@@QEAA?AU0@PEBG@Z; CSrmDebugInfo::operator<<(ushort const *)
0x180019ab7  nop
0x180019ab8  mov     r8d, ebx; dwMessageId
0x180019abb  lea     rdx, [rbp+150h+var_158]; this
0x180019abf  mov     rcx, rax; struct CSrmDebugInfo *
0x180019ac2  call    ??6CSrmDebugInfo@@QEAA?AU0@J@Z; CSrmDebugInfo::operator<<(long)
0x180019ac7  nop
0x180019ac8  mov     r9d, 1
0x180019ace  mov     r8, rax
0x180019ad1  mov     edx, 80042009h
0x180019ad6  mov     rcx, rsi
0x180019ad9  call    ?LogError@CSrmFunctionTracer@@QEAAXKUCSrmDebugInfo@@G@Z; CSrmFunctionTracer::LogError(ulong,CSrmDebugInfo,ushort)
0x180019ade  nop
0x180019adf  lea     rcx, [rbp+150h+var_C8]; this
0x180019ae6  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x180019aeb  nop
0x180019aec  lea     rcx, [rsp+250h+var_1E8]; this
0x180019af1  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x180019af6  lea     rax, [rsp+250h+var_1E8]
0x180019afb  mov     [rsp+250h+pExceptionObject], rax
0x180019b00  mov     rdx, r14; struct CSrmDebugInfo *
0x180019b03  lea     rcx, [rsp+250h+var_1E8]; this
0x180019b08  call    ??0CSrmDebugInfo@@QEAA@AEBU0@@Z; CSrmDebugInfo::CSrmDebugInfo(CSrmDebugInfo const &)
0x180019b0d  nop
0x180019b0e  mov     dword ptr [rsp+250h+Args], ebx
0x180019b12  mov     [rsp+250h+Format], rdi
0x180019b17  mov     [rsp+250h+var_230], r15
0x180019b1c  lea     r9, aUnexpectedErro_0; "Unexpected error: %s - %s [hr = 0x%08lx"...
0x180019b23  mov     r8d, 80045316h
0x180019b29  mov     rdx, rax
0x180019b2c  mov     rcx, rsi
0x180019b2f  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x180019b35  lea     rcx, [rsp+250h+var_1F0]; this
0x180019b3a  call    ?GetBuffer@CSrmOutputBuffer@@QEAAPEAGXZ; CSrmOutputBuffer::GetBuffer(void)
0x180019b3f  mov     r9, rax
0x180019b42  lea     rax, [rsp+250h+var_1E8]
0x180019b47  mov     [rsp+250h+var_208], rax
0x180019b4c  mov     rdx, r14; struct CSrmDebugInfo *
0x180019b4f  lea     rcx, [rsp+250h+var_1E8]; this
0x180019b54  call    ??0CSrmDebugInfo@@QEAA@AEBU0@@Z; CSrmDebugInfo::CSrmDebugInfo(CSrmDebugInfo const &)
0x180019b59  nop
0x180019b5a  mov     [rsp+250h+Format], rdi
0x180019b5f  mov     [rsp+250h+var_230], r9
0x180019b64  lea     r9, aOutOfMemoryDet_0; "Out of memory detected. %s - %s"
0x180019b6b  mov     r8d, 8007000Eh
0x180019b71  mov     rdx, rax
0x180019b74  mov     rcx, rsi
0x180019b77  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
```
