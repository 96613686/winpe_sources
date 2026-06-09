# ItSpBatteryRemainingCallback(void *,ulong,void *)

- ea: `0x1800449f0`
- end: `0x180044bb1`
- name: `?ItSpBatteryRemainingCallback@@YAKPEAXK0@Z`
- size: `449`
- prototype: `unsigned int __fastcall(struct _ITSRV_GLOBAL_CONTEXT *, unsigned int, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000a460`
- `0x1800449f0`
- `0x180077880`
- `0x1800829fa`
- `0x180082a40`

## import_xrefs

- `msvcrt!fflush` at `0x180044b3e`
- `msvcrt!fflush` at `0x180044b3e`
- `msvcrt!fclose` at `0x180044b4f`
- `msvcrt!fclose` at `0x180044b4f`
- `msvcrt!fputws` at `0x180044b2d`
- `msvcrt!fputws` at `0x180044b2d`
- `msvcrt!fopen_s` at `0x180044ad7`
- `msvcrt!fopen_s` at `0x180044ad7`
- `ntdll!EtwEventEnabled` at `0x180044a54`
- `ntdll!EtwEventEnabled` at `0x180044a54`
- `ntdll!EtwEventWrite` at `0x180044aa5`
- `ntdll!EtwEventWrite` at `0x180044aa5`

## string_xrefs

- `0x180044acb`: `TaskScheduler.log`
- `0x180044af9`: `EventWrite error`

## pseudocode

```c
unsigned int __fastcall ItSpBatteryRemainingCallback(
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
0x1800449f0  mov     [rsp-8+arg_8], rbx
0x1800449f5  push    rbp
0x1800449f6  push    rsi
0x1800449f7  push    rdi
0x1800449f8  lea     rbp, [rsp-770h]
0x180044a00  sub     rsp, 870h
0x180044a07  mov     rax, cs:__security_cookie
0x180044a0e  xor     rax, rsp
0x180044a11  mov     [rbp+780h+var_20], rax
0x180044a18  mov     rdi, rcx
0x180044a1b  cmp     edx, 8013h
0x180044a21  jnz     loc_180044B89
0x180044a27  cmp     dword ptr [r8+10h], 4
0x180044a2c  jnz     loc_180044B89
0x180044a32  mov     rsi, cs:?g_pEventManager@@3PEAVEventManager@@EA; EventManager * g_pEventManager
0x180044a39  mov     ebx, [r8+14h]
0x180044a3d  mov     [rsp+880h+var_848], ebx
0x180044a41  mov     rcx, [rsi]
0x180044a44  test    rcx, rcx
0x180044a47  jz      loc_180044B5B
0x180044a4d  lea     rdx, ItSpEvt_PowerNotificationReceived
0x180044a54  call    cs:__imp_EtwEventEnabled
0x180044a5b  nop     dword ptr [rax+rax+00h]
0x180044a60  test    al, al
0x180044a62  jz      loc_180044B5B
0x180044a68  mov     rcx, [rsi]
0x180044a6b  lea     rax, aBatteryremaini; "BatteryRemaining"
0x180044a72  mov     [rsp+880h+var_840], rax
0x180044a77  lea     r9, [rsp+880h+var_840]
0x180044a7c  lea     rax, [rsp+880h+var_848]
0x180044a81  mov     [rsp+880h+var_838], 22h ; '"'
0x180044a8a  mov     r8d, 2
0x180044a90  mov     [rsp+880h+var_830], rax
0x180044a95  lea     rdx, ItSpEvt_PowerNotificationReceived
0x180044a9c  mov     [rsp+880h+var_828], 4
0x180044aa5  call    cs:__imp_EtwEventWrite
0x180044aac  nop     dword ptr [rax+rax+00h]
0x180044ab1  mov     esi, eax
0x180044ab3  test    eax, eax
0x180044ab5  jz      loc_180044B5B
0x180044abb  lea     r8, Mode; "a+"
0x180044ac2  mov     [rsp+880h+Stream], 0
0x180044acb  lea     rdx, FileName; "TaskScheduler.log"
0x180044ad2  lea     rcx, [rsp+880h+Stream]; Stream
0x180044ad7  call    cs:__imp_fopen_s
0x180044ade  nop     dword ptr [rax+rax+00h]
0x180044ae3  test    eax, eax
0x180044ae5  jnz     short loc_180044B5B
0x180044ae7  xor     edx, edx; Val
0x180044ae9  lea     rcx, [rsp+880h+Buffer]; void *
0x180044aee  mov     r8d, 800h; Size
0x180044af4  call    memset_0
0x180044af9  lea     r9, aEventwriteErro; "EventWrite error"
0x180044b00  mov     [rsp+880h+var_860], esi
0x180044b04  lea     r8, aSD; "%s, (%d)\n"
0x180044b0b  mov     edx, 400h; unsigned __int64
0x180044b10  lea     rcx, [rsp+880h+Buffer]; unsigned __int16 *
0x180044b15  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180044b1a  mov     rdx, [rsp+880h+Stream]; Stream
0x180044b1f  lea     rcx, [rsp+880h+Buffer]; Buffer
0x180044b24  xor     eax, eax
0x180044b26  mov     [rbp+780h+var_22], ax
0x180044b2d  call    cs:__imp_fputws
0x180044b34  nop     dword ptr [rax+rax+00h]
0x180044b39  mov     rcx, [rsp+880h+Stream]; Stream
0x180044b3e  call    cs:__imp_fflush
0x180044b45  nop     dword ptr [rax+rax+00h]
0x180044b4a  mov     rcx, [rsp+880h+Stream]; Stream
0x180044b4f  call    cs:__imp_fclose
0x180044b56  nop     dword ptr [rax+rax+00h]
0x180044b5b  mov     edx, ebx
0x180044b5d  xor     ecx, ecx; struct _TP_WORK **
0x180044b5f  xchg    edx, [rdi+340h]
0x180044b65  xor     eax, eax
0x180044b67  lock cmpxchg [rdi+330h], ecx
0x180044b6f  cmp     edx, eax
0x180044b71  jb      short loc_180044B7B
0x180044b73  cmp     ebx, eax
0x180044b75  jb      short loc_180044B7F
0x180044b77  xor     eax, eax
0x180044b79  jmp     short loc_180044B8E
0x180044b7b  cmp     ebx, eax
0x180044b7d  jb      short loc_180044B77
0x180044b7f  mov     rdx, rdi; struct _ITSRV_GLOBAL_CONTEXT *
0x180044b82  call    ?ItSpSubmitThreadpoolWork@@YAKPEAPEAU_TP_WORK@@PEAU_ITSRV_GLOBAL_CONTEXT@@P6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU1@@Z@Z; ItSpSubmitThreadpoolWork(_TP_WORK * *,_ITSRV_GLOBAL_CONTEXT *,void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *))
0x180044b87  jmp     short loc_180044B8E
0x180044b89  mov     eax, 57h ; 'W'
0x180044b8e  mov     rcx, [rbp+780h+var_20]
0x180044b95  xor     rcx, rsp; StackCookie
0x180044b98  call    __security_check_cookie
0x180044b9d  mov     rbx, [rsp+880h+arg_8]
0x180044ba5  add     rsp, 870h
0x180044bac  pop     rdi
0x180044bad  pop     rsi
0x180044bae  pop     rbp
0x180044baf  retn
```
