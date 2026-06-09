# LsaQuerySecurityContextToken(_SecHandle *,void * *)

- ea: `0x1800135e0`
- end: `0x1800136d5`
- name: `?LsaQuerySecurityContextToken@@YAJPEAU_SecHandle@@PEAPEAX@Z`
- size: `245`
- prototype: `int(struct _SecHandle *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003ee0`
- `0x180005cc0`
- `0x1800135e0`
- `0x180023010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800136b0`
- `ntdll!RtlNtStatusToDosError` at `0x1800136b0`
- `ntdll!NtDuplicateObject` at `0x180013694`
- `ntdll!NtDuplicateObject` at `0x180013694`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001362a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800136b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001362a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800136b8`

## pseudocode

```c
__int64 __fastcall LsaQuerySecurityContextToken(struct _SecHandle *a1, void **a2)
{
  NTSTATUS v4; // ebx
  _QWORD *v6; // rcx
  __int64 (__fastcall *v7)(ULONG_PTR, HANDLE *); // rax
  ULONG v8; // eax
  HLOCAL *v9; // [rsp+50h] [rbp+8h] BYREF
  HANDLE SourceHandle; // [rsp+60h] [rbp+18h] BYREF

  v9 = 0;
  SourceHandle = 0;
  v4 = SecLocatePackageById((HLOCAL)a1->dwLower, &v9);
  if ( v4 >= 0 )
  {
    if ( LsaPackageShutdown )
    {
      SetLastError(0x45Bu);
      return 2148074245LL;
    }
    v6 = v9[23];
    if ( v6 && (v7 = (__int64 (__fastcall *)(ULONG_PTR, HANDLE *))v6[6]) != 0 )
    {
      v4 = v7(a1->dwUpper, &SourceHandle);
      if ( v4 >= 0 )
      {
        if ( SourceHandle )
        {
          v4 = NtDuplicateObject((HANDLE)0xFFFFFFFFFFFFFFFFLL, SourceHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL, a2, 0, 0, 2u);
          if ( v4 >= 0 )
            return SspNtStatusToSecStatus(v4);
        }
        else
        {
          v4 = -2146893045;
        }
      }
    }
    else
    {
      v4 = -2146893054;
    }
  }
  v8 = RtlNtStatusToDosError(v4);
  SetLastError(v8);
  return SspNtStatusToSecStatus(v4);
}

```

## disassembly

```asm
0x1800135e0  mov     rax, rsp
0x1800135e3  mov     [rax+10h], rbx
0x1800135e7  mov     [rax+20h], rsi
0x1800135eb  push    rdi
0x1800135ec  sub     rsp, 40h
0x1800135f0  mov     rsi, rdx
0x1800135f3  mov     qword ptr [rax+8], 0
0x1800135fb  mov     rdi, rcx
0x1800135fe  mov     qword ptr [rax+18h], 0
0x180013606  mov     rcx, [rcx]
0x180013609  lea     rdx, [rax+8]
0x18001360d  call    SecLocatePackageById
0x180013612  mov     ebx, eax
0x180013614  test    eax, eax
0x180013616  js      loc_1800136AE
0x18001361c  cmp     cs:?LsaPackageShutdown@@3HA, 0; int LsaPackageShutdown
0x180013623  jz      short loc_18001363A
0x180013625  mov     ecx, 45Bh; dwErrCode
0x18001362a  call    cs:__imp_SetLastError
0x180013630  mov     eax, 80090305h
0x180013635  jmp     loc_1800136C5
0x18001363a  mov     rax, [rsp+48h+arg_0]
0x18001363f  mov     rcx, [rax+0B8h]
0x180013646  test    rcx, rcx
0x180013649  jz      short loc_1800136A9
0x18001364b  mov     rax, [rcx+30h]
0x18001364f  test    rax, rax
0x180013652  jz      short loc_1800136A9
0x180013654  mov     rcx, [rdi+8]
0x180013658  lea     rdx, [rsp+48h+SourceHandle]
0x18001365d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013662  mov     ebx, eax
0x180013664  test    eax, eax
0x180013666  js      short loc_1800136AE
0x180013668  mov     rdx, [rsp+48h+SourceHandle]; SourceHandle
0x18001366d  test    rdx, rdx
0x180013670  jz      short loc_1800136A2
0x180013672  or      rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x180013676  mov     [rsp+48h+Options], 2; Options
0x18001367e  mov     r8, rcx; TargetProcessHandle
0x180013681  mov     [rsp+48h+HandleAttributes], 0; HandleAttributes
0x180013689  mov     r9, rsi; TargetHandle
0x18001368c  mov     [rsp+48h+DesiredAccess], 0; DesiredAccess
0x180013694  call    cs:__imp_NtDuplicateObject
0x18001369a  mov     ebx, eax
0x18001369c  test    eax, eax
0x18001369e  js      short loc_1800136AE
0x1800136a0  jmp     short loc_1800136BE
0x1800136a2  mov     ebx, 8009030Bh
0x1800136a7  jmp     short loc_1800136AE
0x1800136a9  mov     ebx, 80090302h
0x1800136ae  mov     ecx, ebx; Status
0x1800136b0  call    cs:__imp_RtlNtStatusToDosError
0x1800136b6  mov     ecx, eax; dwErrCode
0x1800136b8  call    cs:__imp_SetLastError
0x1800136be  mov     ecx, ebx
0x1800136c0  call    SspNtStatusToSecStatus
0x1800136c5  mov     rbx, [rsp+48h+arg_8]
0x1800136ca  mov     rsi, [rsp+48h+arg_18]
0x1800136cf  add     rsp, 40h
0x1800136d3  pop     rdi
0x1800136d4  retn
```
