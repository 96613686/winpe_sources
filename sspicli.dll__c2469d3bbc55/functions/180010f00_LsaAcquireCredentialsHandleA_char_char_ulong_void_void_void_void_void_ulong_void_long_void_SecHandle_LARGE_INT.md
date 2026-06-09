# LsaAcquireCredentialsHandleA(char *,char *,ulong,void *,void *,void (*)(void *,void *,ulong,void * *,long *),void *,_SecHandle *,_LARGE_INTEGER *)

- ea: `0x180010f00`
- end: `0x1800110e6`
- name: `?LsaAcquireCredentialsHandleA@@YAJPEAD0KPEAX1P6AX11KPEAPEAXPEAJ@Z1PEAU_SecHandle@@PEAT_LARGE_INTEGER@@@Z`
- size: `486`
- prototype: `__int64 __usercall@<rax>(PCSZ Source@<rcx>, char *@<rdx>, unsigned int@<r8d>, void *@<r9>, void *, void (*)(void *, void *, unsigned int, void **, int *), void *, struct _SecHandle *, union _LARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005cc0`
- `0x180006548`
- `0x180007b58`
- `0x18000a0a0`
- `0x18000a108`
- `0x18000e8e4`
- `0x180010f00`
- `0x180018600`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180010f62`
- `ntdll!RtlNtStatusToDosError` at `0x180010f62`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x180010fb6`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x180010fd8`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x180010fb6`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x180010fd8`
- `ntdll!RtlFreeUnicodeString` at `0x180010fe6`
- `ntdll!RtlFreeUnicodeString` at `0x1800110af`
- `ntdll!RtlFreeUnicodeString` at `0x1800110c0`
- `ntdll!RtlFreeUnicodeString` at `0x180010fe6`
- `ntdll!RtlFreeUnicodeString` at `0x1800110af`
- `ntdll!RtlFreeUnicodeString` at `0x1800110c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010f6a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010f6a`

## pseudocode

```c
__int64 __fastcall LsaAcquireCredentialsHandleA(
        PCSZ Source,
        char *a2,
        int a3,
        __int64 a4,
        _DWORD *a5,
        void (*a6)(void *, void *, unsigned int, void **, int *),
        void *a7,
        struct _SecHandle *a8,
        union _LARGE_INTEGER *a9)
{
  char v9; // r14
  SECURITY_STATUS Package; // ebx
  ULONG v14; // eax
  _DWORD *v16; // rdi
  int v17; // [rsp+20h] [rbp-71h]
  PVOID BufferAddress; // [rsp+60h] [rbp-31h] BYREF
  struct _DLL_SECURITY_PACKAGE *v19; // [rsp+68h] [rbp-29h]
  struct _UNICODE_STRING UnicodeString; // [rsp+70h] [rbp-21h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+80h] [rbp-11h] BYREF
  struct _SecHandle v22; // [rsp+90h] [rbp-1h] BYREF
  ULONG BufferSize; // [rsp+D8h] [rbp+47h] BYREF

  BufferAddress = 0;
  v9 = 0;
  BufferSize = 0;
  v19 = 0;
  UnicodeString = 0;
  Destination = 0;
  v22 = 0;
  if ( !a2 )
  {
    Package = -805306355;
LABEL_3:
    v14 = RtlNtStatusToDosError(Package);
    SetLastError(v14);
    goto LABEL_4;
  }
  if ( !RtlCreateUnicodeStringFromAsciiz(&Destination, a2) )
  {
LABEL_10:
    Package = -2146893056;
    goto LABEL_3;
  }
  if ( Source && *Source )
  {
    if ( !RtlCreateUnicodeStringFromAsciiz(&UnicodeString, Source) )
    {
      RtlFreeUnicodeString(&Destination);
      goto LABEL_10;
    }
  }
  else
  {
    UnicodeString = (struct _UNICODE_STRING)xmmword_180040008;
  }
  v16 = a5;
  if ( (NtCurrentPeb()->BitField & 2) != 0 && a5 )
  {
    Package = SecLocatePackageExA(0);
    if ( Package < 0 )
      goto LABEL_3;
    Package = LsapMarshallAuthData(v19, v16, &BufferAddress, &BufferSize);
    if ( Package < 0 )
      goto LABEL_3;
    Package = LsaInsertProtectedProcessAddress(BufferAddress, BufferSize);
    if ( Package < 0 )
      goto LABEL_3;
    v16 = BufferAddress;
    v9 = 1;
  }
  Package = SspipAcquireCredentialsHandle(
              (__int64)&UnicodeString,
              (__int64)&Destination,
              a3,
              a4,
              v17,
              (__int64)v16,
              (__int64)a6,
              (__int64)a7,
              16,
              &v22,
              (__int64 *)a9);
  RtlFreeUnicodeString(&Destination);
  if ( UnicodeString.Buffer )
    RtlFreeUnicodeString(&UnicodeString);
  if ( Package < 0 )
    goto LABEL_3;
  *a8 = v22;
LABEL_4:
  if ( v9 )
    LsaRemoveProtectedProcessAddress(BufferAddress, BufferSize);
  if ( BufferAddress )
    SspiLocalFree(BufferAddress);
  return SspNtStatusToSecStatus((unsigned int)Package);
}

```

## disassembly

```asm
0x180010f00  mov     [rsp-8+arg_0], rbx
0x180010f05  mov     [rsp-8+arg_10], rsi
0x180010f0a  push    rbp
0x180010f0b  push    rdi
0x180010f0c  push    r12
0x180010f0e  push    r14
0x180010f10  push    r15
0x180010f12  lea     rbp, [rsp-0Fh]
0x180010f17  sub     rsp, 0A0h
0x180010f1e  xorps   xmm0, xmm0
0x180010f21  mov     [rbp+2Fh+BufferAddress], 0
0x180010f29  xor     r14b, r14b
0x180010f2c  mov     [rbp+2Fh+BufferSize], 0
0x180010f33  mov     [rbp+2Fh+var_58], 0
0x180010f3b  xorps   xmm1, xmm1
0x180010f3e  mov     r15, r9
0x180010f41  mov     r12d, r8d
0x180010f44  mov     rsi, rdx
0x180010f47  mov     rbx, rcx
0x180010f4a  movups  xmmword ptr [rbp+2Fh+UnicodeString.Length], xmm0
0x180010f4e  movups  xmmword ptr [rbp+2Fh+Destination.Length], xmm1
0x180010f52  movups  [rbp+2Fh+var_30], xmm0
0x180010f56  test    rdx, rdx
0x180010f59  jnz     short loc_180010FB2
0x180010f5b  mov     ebx, 0D000000Dh
0x180010f60  mov     ecx, ebx; Status
0x180010f62  call    cs:__imp_RtlNtStatusToDosError
0x180010f68  mov     ecx, eax; dwErrCode
0x180010f6a  call    cs:__imp_SetLastError
0x180010f70  test    r14b, r14b
0x180010f73  jz      short loc_180010F81
0x180010f75  mov     edx, [rbp+2Fh+BufferSize]; BufferSize
0x180010f78  mov     rcx, [rbp+2Fh+BufferAddress]; BufferAddress
0x180010f7c  call    LsaRemoveProtectedProcessAddress
0x180010f81  mov     rcx, [rbp+2Fh+BufferAddress]; DataBuffer
0x180010f85  test    rcx, rcx
0x180010f88  jz      short loc_180010F8F
0x180010f8a  call    SspiLocalFree
0x180010f8f  mov     ecx, ebx
0x180010f91  call    SspNtStatusToSecStatus
0x180010f96  lea     r11, [rsp+0C0h+var_20]
0x180010f9e  mov     rbx, [r11+30h]
0x180010fa2  mov     rsi, [r11+40h]
0x180010fa6  mov     rsp, r11
0x180010fa9  pop     r15
0x180010fab  pop     r14
0x180010fad  pop     r12
0x180010faf  pop     rdi
0x180010fb0  pop     rbp
0x180010fb1  retn
0x180010fb2  lea     rcx, [rbp+2Fh+Destination]; Destination
0x180010fb6  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x180010fbc  test    al, al
0x180010fbe  jnz     short loc_180010FC7
0x180010fc0  mov     ebx, 80090300h
0x180010fc5  jmp     short loc_180010F60
0x180010fc7  test    rbx, rbx
0x180010fca  jz      short loc_180010FEE
0x180010fcc  cmp     [rbx], r14b
0x180010fcf  jz      short loc_180010FEE
0x180010fd1  mov     rdx, rbx; Source
0x180010fd4  lea     rcx, [rbp+2Fh+UnicodeString]; Destination
0x180010fd8  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x180010fde  test    al, al
0x180010fe0  jnz     short loc_180010FFA
0x180010fe2  lea     rcx, [rbp+2Fh+Destination]; UnicodeString
0x180010fe6  call    cs:__imp_RtlFreeUnicodeString
0x180010fec  jmp     short loc_180010FC0
0x180010fee  movups  xmm0, cs:xmmword_180040008
0x180010ff5  movdqu  xmmword ptr [rbp+2Fh+UnicodeString.Length], xmm0
0x180010ffa  mov     rax, gs:60h
0x180011003  mov     rdi, [rbp+2Fh+arg_20]
0x180011007  test    byte ptr [rax+3], 2
0x18001100b  jz      short loc_180011065
0x18001100d  test    rdi, rdi
0x180011010  jz      short loc_180011065
0x180011012  lea     r8, [rbp+2Fh+var_58]
0x180011016  mov     rdx, rsi
0x180011019  xor     ecx, ecx; int
0x18001101b  call    SecLocatePackageExA
0x180011020  mov     ebx, eax
0x180011022  test    eax, eax
0x180011024  js      loc_180010F60
0x18001102a  mov     rcx, [rbp+2Fh+var_58]; struct _DLL_SECURITY_PACKAGE *
0x18001102e  lea     r9, [rbp+2Fh+BufferSize]; unsigned int *
0x180011032  lea     r8, [rbp+2Fh+BufferAddress]; void **
0x180011036  mov     rdx, rdi; void *
0x180011039  call    ?LsapMarshallAuthData@@YAJPEAU_DLL_SECURITY_PACKAGE@@PEAXPEAPEAXPEAK@Z; LsapMarshallAuthData(_DLL_SECURITY_PACKAGE *,void *,void * *,ulong *)
0x18001103e  mov     ebx, eax
0x180011040  test    eax, eax
0x180011042  js      loc_180010F60
0x180011048  mov     edx, [rbp+2Fh+BufferSize]; BufferSize
0x18001104b  mov     rcx, [rbp+2Fh+BufferAddress]; BufferAddress
0x18001104f  call    LsaInsertProtectedProcessAddress
0x180011054  mov     ebx, eax
0x180011056  test    eax, eax
0x180011058  js      loc_180010F60
0x18001105e  mov     rdi, [rbp+2Fh+BufferAddress]
0x180011062  mov     r14b, 1
0x180011065  mov     rax, [rbp+2Fh+arg_40]
0x180011069  lea     rdx, [rbp+2Fh+Destination]
0x18001106d  mov     [rsp+0C0h+var_70], rax
0x180011072  lea     rcx, [rbp+2Fh+UnicodeString]
0x180011076  lea     rax, [rbp+2Fh+var_30]
0x18001107a  mov     r9, r15
0x18001107d  mov     [rsp+0C0h+var_78], rax
0x180011082  mov     r8d, r12d
0x180011085  mov     rax, [rbp+2Fh+arg_30]
0x180011089  mov     [rsp+0C0h+var_80], 10h
0x180011091  mov     [rsp+0C0h+var_88], rax
0x180011096  mov     rax, [rbp+2Fh+arg_28]
0x18001109a  mov     [rsp+0C0h+var_90], rax
0x18001109f  mov     [rsp+0C0h+var_98], rdi
0x1800110a4  call    SspipAcquireCredentialsHandle
0x1800110a9  lea     rcx, [rbp+2Fh+Destination]; UnicodeString
0x1800110ad  mov     ebx, eax
0x1800110af  call    cs:__imp_RtlFreeUnicodeString
0x1800110b5  cmp     [rbp+2Fh+UnicodeString.Buffer], 0
0x1800110ba  jz      short loc_1800110C6
0x1800110bc  lea     rcx, [rbp+2Fh+UnicodeString]; UnicodeString
0x1800110c0  call    cs:__imp_RtlFreeUnicodeString
0x1800110c6  test    ebx, ebx
0x1800110c8  js      loc_180010F60
0x1800110ce  mov     rcx, [rbp+2Fh+arg_38]
0x1800110d2  mov     rax, qword ptr [rbp+2Fh+var_30+8]
0x1800110d6  mov     [rcx+8], rax
0x1800110da  mov     rax, qword ptr [rbp+2Fh+var_30]
0x1800110de  mov     [rcx], rax
0x1800110e1  jmp     loc_180010F70
```
