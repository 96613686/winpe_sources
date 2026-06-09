# LsaDeleteSecurityContext(_SecHandle *)

- ea: `0x180005370`
- end: `0x1800053ed`
- name: `?LsaDeleteSecurityContext@@YAJPEAU_SecHandle@@@Z`
- size: `125`
- prototype: `__int64 __fastcall(struct _SecHandle *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002130`
- `0x18001b700`
- `0x18001c130`

## callees

- `0x180005370`
- `0x180005cc0`
- `0x1800061a0`
- `0x1800159dc`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800053dd`
- `ntdll!RtlNtStatusToDosError` at `0x1800053dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800053d0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800053e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800053d0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800053e5`

## pseudocode

```c
__int64 __fastcall LsaDeleteSecurityContext(struct _SecHandle *a1)
{
  NTSTATUS v2; // ebx
  ULONG v4; // eax
  _QWORD v5[3]; // [rsp+20h] [rbp-18h] BYREF

  if ( !a1 )
  {
    v2 = -2146893055;
    goto LABEL_10;
  }
  if ( LsaPackageShutdown )
  {
    SetLastError(0x45Bu);
    v2 = -2146893051;
    goto LABEL_10;
  }
  if ( (unsigned int)DeleteUserModeContext((void **)a1) != 590627 )
  {
    v5[1] = a1->dwUpper;
    v5[0] = a1->dwLower;
    v2 = SspipDeleteSecurityContext(v5);
    if ( v2 >= 0 )
      return SspNtStatusToSecStatus(v2);
LABEL_10:
    v4 = RtlNtStatusToDosError(v2);
    SetLastError(v4);
    return SspNtStatusToSecStatus(v2);
  }
  v2 = 0;
  return SspNtStatusToSecStatus(v2);
}

```

## disassembly

```asm
0x180005370  push    rbx
0x180005372  sub     rsp, 30h
0x180005376  mov     rbx, rcx
0x180005379  test    rcx, rcx
0x18000537c  jz      short loc_1800053C4
0x18000537e  cmp     cs:?LsaPackageShutdown@@3HA, 0; int LsaPackageShutdown
0x180005385  jnz     short loc_1800053CB
0x180005387  call    DeleteUserModeContext
0x18000538c  cmp     eax, 90323h
0x180005391  jnz     short loc_1800053A1
0x180005393  xor     ebx, ebx
0x180005395  mov     ecx, ebx
0x180005397  add     rsp, 30h
0x18000539b  pop     rbx
0x18000539c  jmp     SspNtStatusToSecStatus
0x1800053a1  mov     rax, [rbx+8]
0x1800053a5  lea     rcx, [rsp+38h+var_18]
0x1800053aa  mov     [rsp+38h+var_10], rax
0x1800053af  mov     rax, [rbx]
0x1800053b2  mov     [rsp+38h+var_18], rax
0x1800053b7  call    SspipDeleteSecurityContext
0x1800053bc  mov     ebx, eax
0x1800053be  test    eax, eax
0x1800053c0  jns     short loc_180005395
0x1800053c2  jmp     short loc_1800053DB
0x1800053c4  mov     ebx, 80090301h
0x1800053c9  jmp     short loc_1800053DB
0x1800053cb  mov     ecx, 45Bh; dwErrCode
0x1800053d0  call    cs:__imp_SetLastError
0x1800053d6  mov     ebx, 80090305h
0x1800053db  mov     ecx, ebx; Status
0x1800053dd  call    cs:__imp_RtlNtStatusToDosError
0x1800053e3  mov     ecx, eax; dwErrCode
0x1800053e5  call    cs:__imp_SetLastError
0x1800053eb  jmp     short loc_180005395
```
