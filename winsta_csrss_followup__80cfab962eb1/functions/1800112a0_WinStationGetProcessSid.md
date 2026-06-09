# WinStationGetProcessSid

- ea: `0x1800112a0`
- end: `0x180011329`
- name: `WinStationGetProcessSid`
- size: `137`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180005b40`
- `0x18000a784`
- `0x1800112a0`
- `0x180011330`
- `0x18002ecbc`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800112f8`
- `ntdll!RtlNtStatusToDosError` at `0x1800112f8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011306`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011306`

## string_xrefs

- `0x1800112e5`: `GetSidFromProcessId failed: 0x%x`

## pseudocode

```c
unsigned __int8 __fastcall WinStationGetProcessSid(void *a1, __int64 a2, __int64 a3, __int64 a4, unsigned int *a5)
{
  signed int v5; // edx
  CPublicBinding *v6; // rcx
  struct _FILETIME v7; // r8
  unsigned __int8 *v8; // r9
  union _LARGE_INTEGER v9; // r10
  void *v10; // r11
  char v11; // bl
  int SidFromProcessId; // eax
  NTSTATUS v13; // edi
  DWORD v15; // eax

  if ( !(unsigned int)IsLocalServer(a1) )
    return Legacy_WinStationGetProcessSid(v6, v5, v7, v8, a5);
  v11 = 1;
  SidFromProcessId = GetSidFromProcessId((void *)v5, v9, v10, a5);
  v13 = SidFromProcessId;
  if ( SidFromProcessId < 0 )
  {
    _DbgPrintMessage(8, "GetSidFromProcessId failed: 0x%x", SidFromProcessId);
    v15 = RtlNtStatusToDosError(v13);
    SetLastError(v15);
    return 0;
  }
  return v11;
}

```

## disassembly

```asm
0x1800112a0  mov     [rsp+arg_0], rbx
0x1800112a5  push    rdi
0x1800112a6  sub     rsp, 30h
0x1800112aa  mov     r11, r9
0x1800112ad  mov     r10, r8
0x1800112b0  call    ?IsLocalServer@@YAHPEAX@Z; IsLocalServer(void *)
0x1800112b5  test    eax, eax
0x1800112b7  jz      short loc_180011316
0x1800112b9  mov     r9, [rsp+38h+arg_20]; unsigned int *
0x1800112be  mov     r8, r11; void *
0x1800112c1  movsxd  rcx, edx; void *
0x1800112c4  mov     bl, 1
0x1800112c6  mov     rdx, r10; union _LARGE_INTEGER
0x1800112c9  call    ?GetSidFromProcessId@@YAJPEAXT_LARGE_INTEGER@@0PEAK@Z; GetSidFromProcessId(void *,_LARGE_INTEGER,void *,ulong *)
0x1800112ce  mov     edi, eax
0x1800112d0  test    eax, eax
0x1800112d2  js      short loc_1800112E2
0x1800112d4  mov     al, bl
0x1800112d6  mov     rbx, [rsp+38h+arg_0]
0x1800112db  add     rsp, 30h
0x1800112df  pop     rdi
0x1800112e0  retn
0x1800112e2  mov     r8d, edi
0x1800112e5  lea     rdx, aGetsidfromproc_1; "GetSidFromProcessId failed: 0x%x"
0x1800112ec  mov     ecx, 8; int
0x1800112f1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800112f6  mov     ecx, edi; Status
0x1800112f8  call    cs:__imp_RtlNtStatusToDosError
0x1800112ff  nop     dword ptr [rax+rax+00h]
0x180011304  mov     ecx, eax; dwErrCode
0x180011306  call    cs:__imp_SetLastError
0x18001130d  nop     dword ptr [rax+rax+00h]
0x180011312  xor     bl, bl
0x180011314  jmp     short loc_1800112D4
0x180011316  mov     rax, [rsp+38h+arg_20]
0x18001131b  mov     [rsp+38h+var_18], rax; unsigned int *
0x180011320  call    ?Legacy_WinStationGetProcessSid@@YAEPEAXKU_FILETIME@@PEAEPEAK@Z; Legacy_WinStationGetProcessSid(void *,ulong,_FILETIME,uchar *,ulong *)
0x180011325  mov     bl, al
0x180011327  jmp     short loc_1800112D4
```
