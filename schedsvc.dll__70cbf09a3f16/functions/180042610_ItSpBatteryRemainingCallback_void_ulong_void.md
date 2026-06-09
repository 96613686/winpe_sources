# ItSpBatteryRemainingCallback(void *,ulong,void *)

- ea: `0x180042610`
- end: `0x1800427ac`
- name: `?ItSpBatteryRemainingCallback@@YAKPEAXK0@Z`
- size: `412`
- prototype: `unsigned int __fastcall(struct _ITSRV_GLOBAL_CONTEXT *, unsigned int, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180015740`
- `0x180042610`
- `0x180073bd0`
- `0x18007e68a`
- `0x18007e6d0`

## import_xrefs

- `msvcrt!fflush` at `0x180042746`
- `msvcrt!fflush` at `0x180042746`
- `msvcrt!fclose` at `0x180042751`
- `msvcrt!fclose` at `0x180042751`
- `msvcrt!fputws` at `0x18004273b`
- `msvcrt!fputws` at `0x18004273b`
- `msvcrt!fopen_s` at `0x1800426eb`
- `msvcrt!fopen_s` at `0x1800426eb`
- `ntdll!EtwEventEnabled` at `0x180042674`
- `ntdll!EtwEventEnabled` at `0x180042674`
- `ntdll!EtwEventWrite` at `0x1800426bf`
- `ntdll!EtwEventWrite` at `0x1800426bf`

## string_xrefs

- `0x1800426df`: `TaskScheduler.log`
- `0x180042707`: `EventWrite error`

## pseudocode

```c
DWORD __fastcall ItSpBatteryRemainingCallback(
        struct _ITSRV_GLOBAL_CONTEXT *a1,
        int a2,
        void (*a3)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *))
{
  EventManager *v4; // rsi
  unsigned __int32 v5; // ebx
  __int64 v6; // rcx
  int v7; // esi
  unsigned __int32 v8; // edx
  unsigned __int32 v9; // eax
  FILE *Stream; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int32 v12; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v13[4]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t Buffer[1024]; // [rsp+60h] [rbp-A0h] BYREF

  if ( a2 != 32787 || *((_DWORD *)a3 + 4) != 4 )
    return 87;
  v4 = g_pEventManager;
  v5 = *((_DWORD *)a3 + 5);
  v12 = v5;
  if ( *(_QWORD *)g_pEventManager )
  {
    if ( (unsigned __int8)EtwEventEnabled(*(_QWORD *)g_pEventManager, &ItSpEvt_PowerNotificationReceived) )
    {
      v6 = *(_QWORD *)v4;
      v13[0] = L"BatteryRemaining";
      v13[1] = 34;
      v13[2] = &v12;
      v13[3] = 4;
      v7 = EtwEventWrite(v6, &ItSpEvt_PowerNotificationReceived, 2, v13);
      if ( v7 )
      {
        Stream = 0;
        if ( !fopen_s(&Stream, "TaskScheduler.log", "a+") )
        {
          memset_0(Buffer, 0, sizeof(Buffer));
          StringCchPrintfW(Buffer, 0x400u, L"%s, (%d)\n", L"EventWrite error", v7);
          Buffer[1023] = 0;
          fputws(Buffer, Stream);
          fflush(Stream);
          fclose(Stream);
        }
      }
    }
  }
  v8 = _InterlockedExchange((volatile __int32 *)a1 + 208, v5);
  v9 = _InterlockedCompareExchange((volatile signed __int32 *)a1 + 204, 0, 0);
  if ( v8 < v9 )
  {
    if ( v5 < v9 )
      return 0;
  }
  else if ( v5 >= v9 )
  {
    return 0;
  }
  return ItSpSubmitThreadpoolWork(0, a1, a3);
}

```

## disassembly

```asm
0x180042610  mov     [rsp-8+arg_8], rbx
0x180042615  push    rbp
0x180042616  push    rsi
0x180042617  push    rdi
0x180042618  lea     rbp, [rsp-770h]
0x180042620  sub     rsp, 870h
0x180042627  mov     rax, cs:__security_cookie
0x18004262e  xor     rax, rsp
0x180042631  mov     [rbp+780h+var_20], rax
0x180042638  mov     rdi, rcx
0x18004263b  cmp     edx, 8013h
0x180042641  jnz     loc_180042785
0x180042647  cmp     dword ptr [r8+10h], 4
0x18004264c  jnz     loc_180042785
0x180042652  mov     rsi, cs:?g_pEventManager@@3PEAVEventManager@@EA; EventManager * g_pEventManager
0x180042659  mov     ebx, [r8+14h]
0x18004265d  mov     [rsp+880h+var_848], ebx
0x180042661  mov     rcx, [rsi]
0x180042664  test    rcx, rcx
0x180042667  jz      loc_180042757
0x18004266d  lea     rdx, ItSpEvt_PowerNotificationReceived
0x180042674  call    cs:__imp_EtwEventEnabled
0x18004267a  test    al, al
0x18004267c  jz      loc_180042757
0x180042682  mov     rcx, [rsi]
0x180042685  lea     rax, aBatteryremaini; "BatteryRemaining"
0x18004268c  mov     [rsp+880h+var_840], rax
0x180042691  lea     r9, [rsp+880h+var_840]
0x180042696  lea     rax, [rsp+880h+var_848]
0x18004269b  mov     [rsp+880h+var_838], 22h ; '"'
0x1800426a4  mov     r8d, 2
0x1800426aa  mov     [rsp+880h+var_830], rax
0x1800426af  lea     rdx, ItSpEvt_PowerNotificationReceived
0x1800426b6  mov     [rsp+880h+var_828], 4
0x1800426bf  call    cs:__imp_EtwEventWrite
0x1800426c5  mov     esi, eax
0x1800426c7  test    eax, eax
0x1800426c9  jz      loc_180042757
0x1800426cf  lea     r8, Mode; "a+"
0x1800426d6  mov     [rsp+880h+Stream], 0
0x1800426df  lea     rdx, FileName; "TaskScheduler.log"
0x1800426e6  lea     rcx, [rsp+880h+Stream]; Stream
0x1800426eb  call    cs:__imp_fopen_s
0x1800426f1  test    eax, eax
0x1800426f3  jnz     short loc_180042757
0x1800426f5  xor     edx, edx; Val
0x1800426f7  lea     rcx, [rsp+880h+Buffer]; void *
0x1800426fc  mov     r8d, 800h; Size
0x180042702  call    memset_0
0x180042707  lea     r9, aEventwriteErro; "EventWrite error"
0x18004270e  mov     [rsp+880h+var_860], esi
0x180042712  lea     r8, aSD; "%s, (%d)\n"
0x180042719  mov     edx, 400h; unsigned __int64
0x18004271e  lea     rcx, [rsp+880h+Buffer]; unsigned __int16 *
0x180042723  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180042728  mov     rdx, [rsp+880h+Stream]; Stream
0x18004272d  lea     rcx, [rsp+880h+Buffer]; Buffer
0x180042732  xor     eax, eax
0x180042734  mov     [rbp+780h+var_22], ax
0x18004273b  call    cs:__imp_fputws
0x180042741  mov     rcx, [rsp+880h+Stream]; Stream
0x180042746  call    cs:__imp_fflush
0x18004274c  mov     rcx, [rsp+880h+Stream]; Stream
0x180042751  call    cs:__imp_fclose
0x180042757  mov     edx, ebx
0x180042759  xor     ecx, ecx; struct _TP_WORK **
0x18004275b  xchg    edx, [rdi+340h]
0x180042761  xor     eax, eax
0x180042763  lock cmpxchg [rdi+330h], ecx
0x18004276b  cmp     edx, eax
0x18004276d  jb      short loc_180042777
0x18004276f  cmp     ebx, eax
0x180042771  jb      short loc_18004277B
0x180042773  xor     eax, eax
0x180042775  jmp     short loc_18004278A
0x180042777  cmp     ebx, eax
0x180042779  jb      short loc_180042773
0x18004277b  mov     rdx, rdi; struct _ITSRV_GLOBAL_CONTEXT *
0x18004277e  call    ?ItSpSubmitThreadpoolWork@@YAKPEAPEAU_TP_WORK@@PEAU_ITSRV_GLOBAL_CONTEXT@@P6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU1@@Z@Z; ItSpSubmitThreadpoolWork(_TP_WORK * *,_ITSRV_GLOBAL_CONTEXT *,void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *))
0x180042783  jmp     short loc_18004278A
0x180042785  mov     eax, 57h ; 'W'
0x18004278a  mov     rcx, [rbp+780h+var_20]
0x180042791  xor     rcx, rsp; StackCookie
0x180042794  call    __security_check_cookie
0x180042799  mov     rbx, [rsp+880h+arg_8]
0x1800427a1  add     rsp, 870h
0x1800427a8  pop     rdi
0x1800427a9  pop     rsi
0x1800427aa  pop     rbp
0x1800427ab  retn
```
