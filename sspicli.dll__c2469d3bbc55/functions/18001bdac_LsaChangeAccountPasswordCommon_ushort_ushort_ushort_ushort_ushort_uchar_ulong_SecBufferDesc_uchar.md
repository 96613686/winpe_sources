# LsaChangeAccountPasswordCommon(ushort *,ushort *,ushort *,ushort *,ushort *,uchar,ulong,_SecBufferDesc *,uchar)

- ea: `0x18001bdac`
- end: `0x18001bfb1`
- name: `?LsaChangeAccountPasswordCommon@@YAJPEAG0000EKPEAU_SecBufferDesc@@E@Z`
- size: `517`
- prototype: `__int64 __fastcall(PCSZ Source, PCSZ, PCSZ, PCSZ, PCWSTR SourceString, char, unsigned int, struct _SecBufferDesc *, char)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001bd60`
- `0x18001bfc0`

## callees

- `0x1800011f0`
- `0x180002740`
- `0x180005cc0`
- `0x18000c4f0`
- `0x18001bdac`
- `0x180020adc`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18001be2b`
- `ntdll!RtlInitUnicodeString` at `0x18001be38`
- `ntdll!RtlInitUnicodeString` at `0x18001be45`
- `ntdll!RtlInitUnicodeString` at `0x18001be52`
- `ntdll!RtlInitUnicodeString` at `0x18001be60`
- `ntdll!RtlInitUnicodeString` at `0x18001be2b`
- `ntdll!RtlInitUnicodeString` at `0x18001be38`
- `ntdll!RtlInitUnicodeString` at `0x18001be45`
- `ntdll!RtlInitUnicodeString` at `0x18001be52`
- `ntdll!RtlInitUnicodeString` at `0x18001be60`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18001be6a`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18001be7b`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18001be8c`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18001bea1`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18001beb7`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18001be6a`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18001be7b`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18001be8c`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18001bea1`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18001beb7`
- `ntdll!RtlFreeUnicodeString` at `0x18001bf58`
- `ntdll!RtlFreeUnicodeString` at `0x18001bf62`
- `ntdll!RtlFreeUnicodeString` at `0x18001bf6c`
- `ntdll!RtlFreeUnicodeString` at `0x18001bf76`
- `ntdll!RtlFreeUnicodeString` at `0x18001bf80`
- `ntdll!RtlFreeUnicodeString` at `0x18001bf58`
- `ntdll!RtlFreeUnicodeString` at `0x18001bf62`
- `ntdll!RtlFreeUnicodeString` at `0x18001bf6c`
- `ntdll!RtlFreeUnicodeString` at `0x18001bf76`
- `ntdll!RtlFreeUnicodeString` at `0x18001bf80`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bf8c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bf8c`

## pseudocode

```c
__int64 __fastcall LsaChangeAccountPasswordCommon(
        const WCHAR *Source,
        const WCHAR *a2,
        const WCHAR *a3,
        const WCHAR *a4,
        PCWSTR SourceString,
        char a6,
        unsigned int a7,
        struct _SecBufferDesc *a8,
        char a9)
{
  signed int v13; // ebx
  int v14; // eax
  struct _SecBufferDesc *v15; // rsi
  unsigned int i; // edi
  PSecBuffer pBuffers; // rax
  int v19; // [rsp+50h] [rbp-41h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-39h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+68h] [rbp-29h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+78h] [rbp-19h] BYREF
  struct _UNICODE_STRING v23; // [rsp+88h] [rbp-9h] BYREF
  struct _UNICODE_STRING v24; // [rsp+98h] [rbp+7h] BYREF
  unsigned int v25; // [rsp+D0h] [rbp+3Fh] BYREF

  v25 = 0;
  DestinationString = 0;
  Destination = 0;
  UnicodeString = 0;
  v23 = 0;
  v24 = 0;
  if ( !Source )
  {
    v13 = -805306355;
    goto LABEL_19;
  }
  if ( !(unsigned int)SecpReserveVMSpots(19, &v25) )
    goto LABEL_4;
  if ( a9 )
  {
    RtlInitUnicodeString(&DestinationString, Source);
    RtlInitUnicodeString(&Destination, a2);
    RtlInitUnicodeString(&UnicodeString, a3);
    RtlInitUnicodeString(&v23, a4);
    RtlInitUnicodeString(&v24, SourceString);
    v14 = 0;
  }
  else
  {
    if ( !RtlCreateUnicodeStringFromAsciiz(&DestinationString, (PCSZ)Source)
      || !RtlCreateUnicodeStringFromAsciiz(&Destination, (PCSZ)a2)
      || !RtlCreateUnicodeStringFromAsciiz(&UnicodeString, (PCSZ)a3)
      || !RtlCreateUnicodeStringFromAsciiz(&v23, (PCSZ)a4)
      || !RtlCreateUnicodeStringFromAsciiz(&v24, (PCSZ)SourceString) )
    {
LABEL_4:
      v13 = -2146893056;
      goto LABEL_19;
    }
    v14 = 16;
  }
  v15 = a8;
  v19 = v14;
  v13 = SecpChangeAccountPassword(
          (unsigned int)&DestinationString,
          (unsigned int)&Destination,
          (unsigned int)&UnicodeString,
          (unsigned int)&v23,
          (__int64)&v24,
          a6,
          a7,
          (__int64)a8,
          (__int64)&v19);
  if ( v15 )
  {
    for ( i = 0; i < v15->cBuffers; ++i )
    {
      pBuffers = v15->pBuffers;
      if ( pBuffers[i].BufferType == 15 && pBuffers[i].cbBuffer )
        SecpAddVMEx(pBuffers[i].pvBuffer, 0, &v25);
    }
  }
LABEL_19:
  SecpReleaseVMSpots(v25);
  if ( !a9 )
  {
    RtlFreeUnicodeString(&DestinationString);
    RtlFreeUnicodeString(&Destination);
    RtlFreeUnicodeString(&UnicodeString);
    RtlFreeUnicodeString(&v23);
    RtlFreeUnicodeString(&v24);
  }
  if ( v13 < 0 )
    SetLastError(v13);
  return SspNtStatusToSecStatus((unsigned int)v13);
}

```

## disassembly

```asm
0x18001bdac  mov     [rsp-8+arg_8], rbx
0x18001bdb1  mov     [rsp-8+arg_10], rsi
0x18001bdb6  push    rbp
0x18001bdb7  push    rdi
0x18001bdb8  push    r14
0x18001bdba  lea     rbp, [rsp-1Fh]
0x18001bdbf  sub     rsp, 0B0h
0x18001bdc6  mov     [rbp+2Fh+arg_0], 0
0x18001bdcd  xorps   xmm0, xmm0
0x18001bdd0  xorps   xmm1, xmm1
0x18001bdd3  mov     rsi, r9
0x18001bdd6  mov     r14, r8
0x18001bdd9  mov     rdi, rdx
0x18001bddc  mov     rbx, rcx
0x18001bddf  movups  xmmword ptr [rbp+2Fh+DestinationString.Length], xmm0
0x18001bde3  movups  xmmword ptr [rbp+2Fh+Destination.Length], xmm1
0x18001bde7  movups  xmmword ptr [rbp+2Fh+UnicodeString.Length], xmm0
0x18001bdeb  movups  xmmword ptr [rbp+2Fh+var_38.Length], xmm1
0x18001bdef  movups  xmmword ptr [rbp+2Fh+var_28.Length], xmm0
0x18001bdf3  test    rcx, rcx
0x18001bdf6  jnz     short loc_18001BE02
0x18001bdf8  mov     ebx, 0D000000Dh
0x18001bdfd  jmp     loc_18001BF46
0x18001be02  lea     rdx, [rbp+2Fh+arg_0]
0x18001be06  mov     ecx, 13h
0x18001be0b  call    SecpReserveVMSpots
0x18001be10  test    eax, eax
0x18001be12  jnz     short loc_18001BE1E
0x18001be14  mov     ebx, 80090300h
0x18001be19  jmp     loc_18001BF46
0x18001be1e  cmp     [rbp+2Fh+arg_40], 0
0x18001be22  lea     rcx, [rbp+2Fh+DestinationString]; Destination
0x18001be26  mov     rdx, rbx; Source
0x18001be29  jz      short loc_18001BE6A
0x18001be2b  call    cs:__imp_RtlInitUnicodeString
0x18001be31  mov     rdx, rdi; SourceString
0x18001be34  lea     rcx, [rbp+2Fh+Destination]; DestinationString
0x18001be38  call    cs:__imp_RtlInitUnicodeString
0x18001be3e  mov     rdx, r14; SourceString
0x18001be41  lea     rcx, [rbp+2Fh+UnicodeString]; DestinationString
0x18001be45  call    cs:__imp_RtlInitUnicodeString
0x18001be4b  mov     rdx, rsi; SourceString
0x18001be4e  lea     rcx, [rbp+2Fh+var_38]; DestinationString
0x18001be52  call    cs:__imp_RtlInitUnicodeString
0x18001be58  mov     rdx, [rbp+2Fh+SourceString]; SourceString
0x18001be5c  lea     rcx, [rbp+2Fh+var_28]; DestinationString
0x18001be60  call    cs:__imp_RtlInitUnicodeString
0x18001be66  xor     eax, eax
0x18001be68  jmp     short loc_18001BECA
0x18001be6a  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x18001be70  test    al, al
0x18001be72  jz      short loc_18001BE14
0x18001be74  mov     rdx, rdi; Source
0x18001be77  lea     rcx, [rbp+2Fh+Destination]; Destination
0x18001be7b  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x18001be81  test    al, al
0x18001be83  jz      short loc_18001BE14
0x18001be85  mov     rdx, r14; Source
0x18001be88  lea     rcx, [rbp+2Fh+UnicodeString]; Destination
0x18001be8c  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x18001be92  test    al, al
0x18001be94  jz      loc_18001BE14
0x18001be9a  mov     rdx, rsi; Source
0x18001be9d  lea     rcx, [rbp+2Fh+var_38]; Destination
0x18001bea1  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x18001bea7  test    al, al
0x18001bea9  jz      loc_18001BE14
0x18001beaf  mov     rdx, [rbp+2Fh+SourceString]; Source
0x18001beb3  lea     rcx, [rbp+2Fh+var_28]; Destination
0x18001beb7  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x18001bebd  test    al, al
0x18001bebf  jz      loc_18001BE14
0x18001bec5  mov     eax, 10h
0x18001beca  mov     rsi, [rbp+2Fh+arg_38]
0x18001bece  lea     r9, [rbp+2Fh+var_38]
0x18001bed2  mov     [rbp+2Fh+var_70], eax
0x18001bed5  lea     r8, [rbp+2Fh+UnicodeString]
0x18001bed9  lea     rax, [rbp+2Fh+var_70]
0x18001bedd  mov     [rsp+0C0h+var_80], rax
0x18001bee2  lea     rdx, [rbp+2Fh+Destination]
0x18001bee6  mov     eax, [rbp+2Fh+arg_30]
0x18001bee9  lea     rcx, [rbp+2Fh+DestinationString]
0x18001beed  mov     [rsp+0C0h+var_88], rsi
0x18001bef2  mov     [rsp+0C0h+var_90], eax
0x18001bef6  mov     al, [rbp+2Fh+arg_28]
0x18001bef9  mov     [rsp+0C0h+var_98], al
0x18001befd  lea     rax, [rbp+2Fh+var_28]
0x18001bf01  mov     [rsp+0C0h+var_A0], rax
0x18001bf06  call    SecpChangeAccountPassword
0x18001bf0b  mov     ebx, eax
0x18001bf0d  test    rsi, rsi
0x18001bf10  jz      short loc_18001BF46
0x18001bf12  xor     edi, edi
0x18001bf14  cmp     [rsi+4], edi
0x18001bf17  jbe     short loc_18001BF46
0x18001bf19  mov     rax, [rsi+8]
0x18001bf1d  mov     ecx, edi
0x18001bf1f  add     rcx, rcx
0x18001bf22  cmp     dword ptr [rax+rcx*8+4], 0Fh
0x18001bf27  jnz     short loc_18001BF3F
0x18001bf29  cmp     dword ptr [rax+rcx*8], 0
0x18001bf2d  jz      short loc_18001BF3F
0x18001bf2f  mov     rcx, [rax+rcx*8+8]
0x18001bf34  lea     r8, [rbp+2Fh+arg_0]
0x18001bf38  xor     edx, edx
0x18001bf3a  call    SecpAddVMEx
0x18001bf3f  inc     edi
0x18001bf41  cmp     edi, [rsi+4]
0x18001bf44  jb      short loc_18001BF19
0x18001bf46  mov     ecx, [rbp+2Fh+arg_0]
0x18001bf49  call    SecpReleaseVMSpots
0x18001bf4e  cmp     [rbp+2Fh+arg_40], 0
0x18001bf52  jnz     short loc_18001BF86
0x18001bf54  lea     rcx, [rbp+2Fh+DestinationString]; UnicodeString
0x18001bf58  call    cs:__imp_RtlFreeUnicodeString
0x18001bf5e  lea     rcx, [rbp+2Fh+Destination]; UnicodeString
0x18001bf62  call    cs:__imp_RtlFreeUnicodeString
0x18001bf68  lea     rcx, [rbp+2Fh+UnicodeString]; UnicodeString
0x18001bf6c  call    cs:__imp_RtlFreeUnicodeString
0x18001bf72  lea     rcx, [rbp+2Fh+var_38]; UnicodeString
0x18001bf76  call    cs:__imp_RtlFreeUnicodeString
0x18001bf7c  lea     rcx, [rbp+2Fh+var_28]; UnicodeString
0x18001bf80  call    cs:__imp_RtlFreeUnicodeString
0x18001bf86  test    ebx, ebx
0x18001bf88  jns     short loc_18001BF92
0x18001bf8a  mov     ecx, ebx; dwErrCode
0x18001bf8c  call    cs:__imp_SetLastError
0x18001bf92  mov     ecx, ebx
0x18001bf94  call    SspNtStatusToSecStatus
0x18001bf99  lea     r11, [rsp+0C0h+var_10]
0x18001bfa1  mov     rbx, [r11+28h]
0x18001bfa5  mov     rsi, [r11+30h]
0x18001bfa9  mov     rsp, r11
0x18001bfac  pop     r14
0x18001bfae  pop     rdi
0x18001bfaf  pop     rbp
0x18001bfb0  retn
```
