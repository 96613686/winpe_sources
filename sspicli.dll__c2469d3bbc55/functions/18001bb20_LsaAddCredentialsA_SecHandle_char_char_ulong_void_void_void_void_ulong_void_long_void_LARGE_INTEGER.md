# LsaAddCredentialsA(_SecHandle *,char *,char *,ulong,void *,void (*)(void *,void *,ulong,void * *,long *),void *,_LARGE_INTEGER *)

- ea: `0x18001bb20`
- end: `0x18001bc41`
- name: `?LsaAddCredentialsA@@YAJPEAU_SecHandle@@PEAD1KPEAXP6AX22KPEAPEAXPEAJ@Z2PEAT_LARGE_INTEGER@@@Z`
- size: `289`
- prototype: `int(struct _SecHandle *, char *, char *, unsigned int, void *, void (*)(void *, void *, unsigned int, void **, int *), void *, union _LARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180005cc0`
- `0x18001bb20`
- `0x180021738`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18001bc20`
- `ntdll!RtlNtStatusToDosError` at `0x18001bc20`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18001bb5e`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18001bb83`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18001bb5e`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18001bb83`
- `ntdll!RtlFreeUnicodeString` at `0x18001bb91`
- `ntdll!RtlFreeUnicodeString` at `0x18001bc03`
- `ntdll!RtlFreeUnicodeString` at `0x18001bc14`
- `ntdll!RtlFreeUnicodeString` at `0x18001bb91`
- `ntdll!RtlFreeUnicodeString` at `0x18001bc03`
- `ntdll!RtlFreeUnicodeString` at `0x18001bc14`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bc28`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bc28`

## pseudocode

```c
__int64 __fastcall LsaAddCredentialsA(
        struct _SecHandle *a1,
        char *a2,
        char *a3,
        int a4,
        void *a5,
        void (*a6)(void *, void *, unsigned int, void **, int *),
        void *a7,
        union _LARGE_INTEGER *a8)
{
  NTSTATUS v11; // ebx
  int v12; // ecx
  ULONG v13; // eax
  struct _UNICODE_STRING UnicodeString; // [rsp+50h] [rbp-19h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+60h] [rbp-9h] BYREF
  _QWORD v17[6]; // [rsp+70h] [rbp+7h] BYREF
  int v18; // [rsp+C0h] [rbp+57h] BYREF

  UnicodeString = 0;
  Destination = 0;
  if ( !a3 )
  {
    v11 = -805306355;
LABEL_13:
    v13 = RtlNtStatusToDosError(v11);
    SetLastError(v13);
    return SspNtStatusToSecStatus((unsigned int)v11);
  }
  if ( !RtlCreateUnicodeStringFromAsciiz(&Destination, a3) )
  {
LABEL_4:
    v11 = -2146893056;
    goto LABEL_13;
  }
  if ( a2 && *a2 )
  {
    if ( !RtlCreateUnicodeStringFromAsciiz(&UnicodeString, a2) )
    {
      RtlFreeUnicodeString(&Destination);
      goto LABEL_4;
    }
  }
  else
  {
    UnicodeString = (struct _UNICODE_STRING)xmmword_180040008;
  }
  v17[1] = a1->dwUpper;
  v17[0] = a1->dwLower;
  v18 = 16;
  v11 = SecpAddCredentials(
          v12,
          (unsigned int)v17,
          (unsigned int)&UnicodeString,
          (unsigned int)&Destination,
          a4,
          (__int64)a5,
          (__int64)a6,
          (__int64)a7,
          (__int64)a8,
          (__int64)&v18);
  RtlFreeUnicodeString(&Destination);
  if ( UnicodeString.Buffer )
    RtlFreeUnicodeString(&UnicodeString);
  if ( v11 < 0 )
    goto LABEL_13;
  return SspNtStatusToSecStatus((unsigned int)v11);
}

```

## disassembly

```asm
0x18001bb20  push    rbp
0x18001bb22  push    rbx
0x18001bb23  push    rsi
0x18001bb24  push    rdi
0x18001bb25  lea     rbp, [rsp-1Fh]
0x18001bb2a  sub     rsp, 88h
0x18001bb31  xorps   xmm0, xmm0
0x18001bb34  xorps   xmm1, xmm1
0x18001bb37  mov     esi, r9d
0x18001bb3a  mov     rbx, rdx
0x18001bb3d  mov     rdi, rcx
0x18001bb40  movups  xmmword ptr [rbp+37h+UnicodeString.Length], xmm0
0x18001bb44  movups  xmmword ptr [rbp+37h+Destination.Length], xmm1
0x18001bb48  test    r8, r8
0x18001bb4b  jnz     short loc_18001BB57
0x18001bb4d  mov     ebx, 0D000000Dh
0x18001bb52  jmp     loc_18001BC1E
0x18001bb57  mov     rdx, r8; Source
0x18001bb5a  lea     rcx, [rbp+37h+Destination]; Destination
0x18001bb5e  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x18001bb64  test    al, al
0x18001bb66  jnz     short loc_18001BB72
0x18001bb68  mov     ebx, 80090300h
0x18001bb6d  jmp     loc_18001BC1E
0x18001bb72  test    rbx, rbx
0x18001bb75  jz      short loc_18001BB99
0x18001bb77  cmp     byte ptr [rbx], 0
0x18001bb7a  jz      short loc_18001BB99
0x18001bb7c  mov     rdx, rbx; Source
0x18001bb7f  lea     rcx, [rbp+37h+UnicodeString]; Destination
0x18001bb83  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x18001bb89  test    al, al
0x18001bb8b  jnz     short loc_18001BBA5
0x18001bb8d  lea     rcx, [rbp+37h+Destination]; UnicodeString
0x18001bb91  call    cs:__imp_RtlFreeUnicodeString
0x18001bb97  jmp     short loc_18001BB68
0x18001bb99  movups  xmm0, cs:xmmword_180040008
0x18001bba0  movdqu  xmmword ptr [rbp+37h+UnicodeString.Length], xmm0
0x18001bba5  mov     rax, [rdi+8]
0x18001bba9  lea     r9, [rbp+37h+Destination]
0x18001bbad  mov     [rbp+37h+var_28], rax
0x18001bbb1  lea     r8, [rbp+37h+UnicodeString]
0x18001bbb5  mov     rax, [rdi]
0x18001bbb8  lea     rdx, [rbp+37h+var_30]
0x18001bbbc  mov     [rbp+37h+var_30], rax
0x18001bbc0  lea     rax, [rbp+37h+arg_10]
0x18001bbc4  mov     [rsp+0A0h+var_58], rax
0x18001bbc9  mov     rax, [rbp+37h+arg_38]
0x18001bbcd  mov     [rsp+0A0h+var_60], rax
0x18001bbd2  mov     rax, [rbp+37h+arg_30]
0x18001bbd6  mov     [rsp+0A0h+var_68], rax
0x18001bbdb  mov     rax, [rbp+37h+arg_28]
0x18001bbdf  mov     [rsp+0A0h+var_70], rax
0x18001bbe4  mov     rax, [rbp+37h+arg_20]
0x18001bbe8  mov     [rsp+0A0h+var_78], rax
0x18001bbed  mov     [rsp+0A0h+var_80], esi
0x18001bbf1  mov     [rbp+37h+arg_10], 10h
0x18001bbf8  call    SecpAddCredentials
0x18001bbfd  lea     rcx, [rbp+37h+Destination]; UnicodeString
0x18001bc01  mov     ebx, eax
0x18001bc03  call    cs:__imp_RtlFreeUnicodeString
0x18001bc09  cmp     [rbp+37h+UnicodeString.Buffer], 0
0x18001bc0e  jz      short loc_18001BC1A
0x18001bc10  lea     rcx, [rbp+37h+UnicodeString]; UnicodeString
0x18001bc14  call    cs:__imp_RtlFreeUnicodeString
0x18001bc1a  test    ebx, ebx
0x18001bc1c  jns     short loc_18001BC2E
0x18001bc1e  mov     ecx, ebx; Status
0x18001bc20  call    cs:__imp_RtlNtStatusToDosError
0x18001bc26  mov     ecx, eax; dwErrCode
0x18001bc28  call    cs:__imp_SetLastError
0x18001bc2e  mov     ecx, ebx
0x18001bc30  call    SspNtStatusToSecStatus
0x18001bc35  add     rsp, 88h
0x18001bc3c  pop     rdi
0x18001bc3d  pop     rsi
0x18001bc3e  pop     rbx
0x18001bc3f  pop     rbp
0x18001bc40  retn
```
