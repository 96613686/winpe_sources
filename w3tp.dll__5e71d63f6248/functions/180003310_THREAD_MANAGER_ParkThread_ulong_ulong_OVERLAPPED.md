# THREAD_MANAGER::ParkThread(ulong,ulong,_OVERLAPPED *)

- ea: `0x180003310`
- end: `0x180003412`
- name: `?ParkThread@THREAD_MANAGER@@CAXKKPEAU_OVERLAPPED@@@Z`
- size: `258`
- prototype: `void __fastcall(unsigned int, unsigned int, struct _OVERLAPPED *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003310`
- `0x180003ccc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800033b0`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800033b0`
- `iisutil!PuDbgPrint` at `0x180003362`
- `iisutil!PuDbgPrint` at `0x1800033ec`
- `iisutil!PuDbgPrint` at `0x180003362`
- `iisutil!PuDbgPrint` at `0x1800033ec`

## string_xrefs

- `0x18000335b`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3tp\thread_manager.cxx`
- `0x1800033e5`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3tp\thread_manager.cxx`
- `0x180003343`: `W3TP: Thread parking\n`
- `0x18000334a`: `THREAD_MANAGER::ParkThread`
- `0x1800033d3`: `THREAD_MANAGER::ParkThread`
- `0x1800033cc`: `W3TP: Thread unparked\n`

## pseudocode

```c
void __fastcall THREAD_MANAGER::ParkThread(__int64 a1, __int64 a2, struct _OVERLAPPED *a3)
{
  signed __int32 v4; // ecx
  _DWORD *Pointer; // rdi
  signed __int32 v6; // ecx
  DWORD v7; // r9d
  DWORD v8; // eax
  DWORD v9; // esi
  HANDLE Handles[3]; // [rsp+30h] [rbp-18h] BYREF

  Handles[0] = a3[2].hEvent;
  Handles[1] = (HANDLE)a3[3].Internal;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3tp\\thread_manager.cxx",
      1497,
      "THREAD_MANAGER::ParkThread",
      "W3TP: Thread parking\n");
  v4 = _InterlockedExchangeAdd((volatile signed __int32 *)&a3[2].16, 1u);
  Pointer = a3[3].Pointer;
  v6 = v4 + 1;
  if ( Pointer && HIDWORD(a3[2].InternalHigh) - v6 <= Pointer[12] )
  {
    _InterlockedDecrement((volatile signed __int32 *)&a3[2].16);
  }
  else
  {
    v7 = 600000;
    if ( Pointer )
      v7 = Pointer[15];
    v8 = WaitForMultipleObjectsEx(2u, Handles, 0, v7, 0);
    _InterlockedDecrement((volatile signed __int32 *)&a3[2].16);
    v9 = v8;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3tp\\thread_manager.cxx",
        1523,
        "THREAD_MANAGER::ParkThread",
        "W3TP: Thread unparked\n");
    if ( v9 == 258 )
      THREAD_POOL_DATA::ThreadPoolStop(Pointer);
  }
}

```

## disassembly

```asm
0x180003310  mov     r11, rsp
0x180003313  mov     [r11+8], rbx
0x180003317  mov     [r11+10h], rsi
0x18000331b  push    rdi
0x18000331c  sub     rsp, 40h
0x180003320  test    cs:g_dwDebugFlags, 3
0x180003327  mov     rbx, r8
0x18000332a  mov     rax, [r8+58h]
0x18000332e  mov     [r11-18h], rax
0x180003332  mov     rax, [r8+60h]
0x180003336  mov     [r11-10h], rax
0x18000333a  jz      short loc_180003368
0x18000333c  mov     rcx, cs:g_pDebug
0x180003343  lea     rax, aW3tpThreadPark; "W3TP: Thread parking\n"
0x18000334a  lea     r9, aThreadManagerP; "THREAD_MANAGER::ParkThread"
0x180003351  mov     [r11-28h], rax
0x180003355  mov     r8d, 5D9h
0x18000335b  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180003362  call    cs:__imp_PuDbgPrint
0x180003368  mov     ecx, 1
0x18000336d  lock xadd [rbx+50h], ecx
0x180003372  mov     rdi, [rbx+70h]
0x180003376  inc     ecx
0x180003378  test    rdi, rdi
0x18000337b  jz      short loc_18000338D
0x18000337d  mov     eax, [rbx+4Ch]
0x180003380  sub     eax, ecx
0x180003382  cmp     eax, [rdi+30h]
0x180003385  jg      short loc_18000338D
0x180003387  lock dec dword ptr [rbx+50h]
0x18000338b  jmp     short loc_180003402
0x18000338d  mov     r9d, 927C0h
0x180003393  test    rdi, rdi
0x180003396  jz      short loc_18000339C
0x180003398  mov     r9d, [rdi+3Ch]; dwMilliseconds
0x18000339c  xor     r8d, r8d; bWaitAll
0x18000339f  mov     [rsp+48h+bAlertable], 0; bAlertable
0x1800033a7  lea     rdx, [rsp+48h+Handles]; lpHandles
0x1800033ac  lea     ecx, [r8+2]; nCount
0x1800033b0  call    cs:__imp_WaitForMultipleObjectsEx
0x1800033b6  lock dec dword ptr [rbx+50h]
0x1800033ba  mov     esi, eax
0x1800033bc  test    cs:g_dwDebugFlags, 3
0x1800033c3  jz      short loc_1800033F2
0x1800033c5  mov     rcx, cs:g_pDebug
0x1800033cc  lea     rax, aW3tpThreadUnpa; "W3TP: Thread unparked\n"
0x1800033d3  lea     r9, aThreadManagerP; "THREAD_MANAGER::ParkThread"
0x1800033da  mov     qword ptr [rsp+48h+bAlertable], rax
0x1800033df  mov     r8d, 5F3h
0x1800033e5  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800033ec  call    cs:__imp_PuDbgPrint
0x1800033f2  cmp     esi, 102h
0x1800033f8  jnz     short loc_180003402
0x1800033fa  mov     rcx, rdi; void *
0x1800033fd  call    ?ThreadPoolStop@THREAD_POOL_DATA@@SAXPEAX@Z; THREAD_POOL_DATA::ThreadPoolStop(void *)
0x180003402  mov     rbx, [rsp+48h+arg_0]
0x180003407  mov     rsi, [rsp+48h+arg_8]
0x18000340c  add     rsp, 40h
0x180003410  pop     rdi
0x180003411  retn
```
