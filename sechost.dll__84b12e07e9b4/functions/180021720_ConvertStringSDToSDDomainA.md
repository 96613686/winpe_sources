# ConvertStringSDToSDDomainA

- ea: `0x180021720`
- end: `0x180021811`
- name: `ConvertStringSDToSDDomainA`
- size: `241`
- prototype: `__int64 __usercall@<rax>(__int64@<rcx>, __int64@<rdx>, PCSZ SourceString@<r8>, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180021720`
- `0x180021820`
- `0x180021cac`

## import_xrefs

- `ntdll!RtlInitAnsiString` at `0x180021792`
- `ntdll!RtlInitAnsiString` at `0x180021792`
- `ntdll!RtlNtStatusToDosError` at `0x1800217ad`
- `ntdll!RtlNtStatusToDosError` at `0x1800217ad`
- `ntdll!RtlValidSid` at `0x18002176a`
- `ntdll!RtlValidSid` at `0x180021780`
- `ntdll!RtlValidSid` at `0x18002176a`
- `ntdll!RtlValidSid` at `0x180021780`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800217ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800217fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800217ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800217fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800217e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800217e3`

## pseudocode

```c
__int64 __fastcall ConvertStringSDToSDDomainA(
        void *a1,
        void *a2,
        PCSZ SourceString,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  NTSTATUS v9; // eax
  DWORD v10; // ecx
  unsigned int v11; // ebx
  HLOCAL hMem[2]; // [rsp+30h] [rbp-48h] BYREF
  struct _STRING DestinationString; // [rsp+40h] [rbp-38h] BYREF

  *(_OWORD *)hMem = 0;
  DestinationString = 0;
  if ( !SourceString || !a5 || !a1 || !RtlValidSid(a1) || a2 && !RtlValidSid(a2) )
  {
    v10 = 87;
    goto LABEL_13;
  }
  RtlInitAnsiString(&DestinationString, SourceString);
  v9 = SddlpAnsiStringToUnicodeString(hMem, &DestinationString);
  if ( v9 < 0 )
  {
    v10 = RtlNtStatusToDosError(v9);
LABEL_13:
    SetLastError(v10);
    return 0;
  }
  v11 = ConvertStringSDToSDDomainW((__int64)a1, (__int64)a2, a5, a6);
  LocalFree(hMem[1]);
  if ( v11 )
    SetLastError(0);
  return v11;
}

```

## disassembly

```asm
0x180021720  push    rbx
0x180021722  push    rbp
0x180021723  push    rsi
0x180021724  push    rdi
0x180021725  push    r14
0x180021727  sub     rsp, 50h
0x18002172b  xorps   xmm0, xmm0
0x18002172e  xorps   xmm1, xmm1
0x180021731  mov     r14d, r9d
0x180021734  mov     rbp, r8
0x180021737  mov     rbx, rdx
0x18002173a  mov     rdi, rcx
0x18002173d  movups  xmmword ptr [rsp+78h+hMem], xmm0
0x180021742  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm1
0x180021747  test    r8, r8
0x18002174a  jz      loc_1800217F9
0x180021750  mov     rsi, [rsp+78h+arg_20]
0x180021758  test    rsi, rsi
0x18002175b  jz      loc_1800217F9
0x180021761  test    rcx, rcx
0x180021764  jz      loc_1800217F9
0x18002176a  call    cs:__imp_RtlValidSid
0x180021770  test    al, al
0x180021772  jz      loc_1800217F9
0x180021778  test    rbx, rbx
0x18002177b  jz      short loc_18002178A
0x18002177d  mov     rcx, rbx; Sid
0x180021780  call    cs:__imp_RtlValidSid
0x180021786  test    al, al
0x180021788  jz      short loc_1800217F9
0x18002178a  mov     rdx, rbp; SourceString
0x18002178d  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x180021792  call    cs:__imp_RtlInitAnsiString
0x180021798  lea     rdx, [rsp+78h+DestinationString]
0x18002179d  lea     rcx, [rsp+78h+hMem]
0x1800217a2  call    SddlpAnsiStringToUnicodeString
0x1800217a7  test    eax, eax
0x1800217a9  jns     short loc_1800217B7
0x1800217ab  mov     ecx, eax; Status
0x1800217ad  call    cs:__imp_RtlNtStatusToDosError
0x1800217b3  mov     ecx, eax
0x1800217b5  jmp     short loc_1800217FE
0x1800217b7  mov     rax, [rsp+78h+arg_28]
0x1800217bf  mov     r9d, r14d
0x1800217c2  mov     r8, [rsp+78h+hMem+8]
0x1800217c7  mov     rdx, rbx; __int64
0x1800217ca  mov     [rsp+78h+var_50], rax; __int64
0x1800217cf  mov     rcx, rdi; __int64
0x1800217d2  mov     [rsp+78h+var_58], rsi; __int64
0x1800217d7  call    ConvertStringSDToSDDomainW
0x1800217dc  mov     rcx, [rsp+78h+hMem+8]; hMem
0x1800217e1  mov     ebx, eax
0x1800217e3  call    cs:__imp_LocalFree
0x1800217e9  test    ebx, ebx
0x1800217eb  jz      short loc_1800217F5
0x1800217ed  xor     ecx, ecx; dwErrCode
0x1800217ef  call    cs:__imp_SetLastError
0x1800217f5  mov     eax, ebx
0x1800217f7  jmp     short loc_180021806
0x1800217f9  mov     ecx, 57h ; 'W'; dwErrCode
0x1800217fe  call    cs:__imp_SetLastError
0x180021804  xor     eax, eax
0x180021806  add     rsp, 50h
0x18002180a  pop     r14
0x18002180c  pop     rdi
0x18002180d  pop     rsi
0x18002180e  pop     rbp
0x18002180f  pop     rbx
0x180021810  retn
```
