# LsaQuerySecurityPackageInfoW(ushort *,_SecPkgInfoW * *)

- ea: `0x18001c530`
- end: `0x18001c5db`
- name: `?LsaQuerySecurityPackageInfoW@@YAJPEAGPEAPEAU_SecPkgInfoW@@@Z`
- size: `171`
- prototype: `__int64 __fastcall(PCWSTR SourceString, struct _SecPkgInfoW **)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800011f0`
- `0x180002740`
- `0x180005cc0`
- `0x180007c90`
- `0x18000c4f0`
- `0x18001c530`
- `0x1800215b0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18001c554`
- `ntdll!RtlInitUnicodeString` at `0x18001c554`
- `ntdll!RtlNtStatusToDosError` at `0x18001c5bb`
- `ntdll!RtlNtStatusToDosError` at `0x18001c5bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c5c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c5c3`

## pseudocode

```c
__int64 __fastcall LsaQuerySecurityPackageInfoW(PCWSTR SourceString, struct _SecPkgInfoW **a2)
{
  NTSTATUS v3; // ebx
  int v4; // eax
  struct _SecPkgInfoW *v5; // rcx
  __int64 v6; // rcx
  ULONG v7; // eax
  struct _UNICODE_STRING v9; // [rsp+20h] [rbp-18h] BYREF
  unsigned int v10; // [rsp+48h] [rbp+10h] BYREF

  v10 = 0;
  v9 = 0;
  RtlInitUnicodeString(&v9, SourceString);
  *a2 = 0;
  if ( !(unsigned int)SecpReserveVMSpots(1, &v10) )
  {
    v3 = -2146893056;
LABEL_7:
    v7 = RtlNtStatusToDosError(v3);
    SetLastError(v7);
    return SspNtStatusToSecStatus(v3);
  }
  v4 = SecpQueryPackageInfo(&v9, a2);
  v5 = *a2;
  v3 = v4;
  if ( v4 < 0 )
  {
    if ( v5 )
    {
      LsaFreeReturnBuffer(v5);
      v6 = v10;
      *a2 = 0;
      SecpReleaseVMSpots(v6);
    }
    goto LABEL_7;
  }
  SecpAddVMEx(v5, 0, &v10);
  return SspNtStatusToSecStatus(v3);
}

```

## disassembly

```asm
0x18001c530  mov     rax, rsp
0x18001c533  mov     [rax+8], rbx
0x18001c537  push    rdi
0x18001c538  sub     rsp, 30h
0x18001c53c  mov     rdi, rdx
0x18001c53f  mov     dword ptr [rax+10h], 0
0x18001c546  mov     rdx, rcx; SourceString
0x18001c549  xorps   xmm0, xmm0
0x18001c54c  lea     rcx, [rax-18h]; DestinationString
0x18001c550  movups  xmmword ptr [rax-18h], xmm0
0x18001c554  call    cs:__imp_RtlInitUnicodeString
0x18001c55a  lea     rdx, [rsp+38h+arg_8]
0x18001c55f  mov     qword ptr [rdi], 0
0x18001c566  mov     ecx, 1
0x18001c56b  call    SecpReserveVMSpots
0x18001c570  test    eax, eax
0x18001c572  jnz     short loc_18001C57B
0x18001c574  mov     ebx, 80090300h
0x18001c579  jmp     short loc_18001C5B9
0x18001c57b  mov     rdx, rdi
0x18001c57e  lea     rcx, [rsp+38h+var_18]
0x18001c583  call    SecpQueryPackageInfo
0x18001c588  mov     rcx, [rdi]; Buffer
0x18001c58b  mov     ebx, eax
0x18001c58d  test    eax, eax
0x18001c58f  js      short loc_18001C59F
0x18001c591  lea     r8, [rsp+38h+arg_8]
0x18001c596  xor     edx, edx
0x18001c598  call    SecpAddVMEx
0x18001c59d  jmp     short loc_18001C5C9
0x18001c59f  test    rcx, rcx
0x18001c5a2  jz      short loc_18001C5B9
0x18001c5a4  call    LsaFreeReturnBuffer
0x18001c5a9  mov     ecx, [rsp+38h+arg_8]
0x18001c5ad  mov     qword ptr [rdi], 0
0x18001c5b4  call    SecpReleaseVMSpots
0x18001c5b9  mov     ecx, ebx; Status
0x18001c5bb  call    cs:__imp_RtlNtStatusToDosError
0x18001c5c1  mov     ecx, eax; dwErrCode
0x18001c5c3  call    cs:__imp_SetLastError
0x18001c5c9  mov     ecx, ebx
0x18001c5cb  call    SspNtStatusToSecStatus
0x18001c5d0  mov     rbx, [rsp+38h+arg_0]
0x18001c5d5  add     rsp, 30h
0x18001c5d9  pop     rdi
0x18001c5da  retn
```
