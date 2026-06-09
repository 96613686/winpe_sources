# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,void *,_GUID const *)

- ea: `0x18004fccc`
- end: `0x18004fdc3`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@PEAX2@Z`
- size: `247`
- prototype: `int(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const struct _GUID *, void *, const struct _GUID *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180038890`
- `0x18004f984`
- `0x180050528`

## callees

- `0x180042530`
- `0x18004fccc`
- `0x18004ff54`
- `0x18007e6d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fd80`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fd80`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004fd32`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004fd32`
- `ntdll!EtwEventEnabled` at `0x18004fd08`
- `ntdll!EtwEventEnabled` at `0x18004fd08`
- `ntdll!EtwEventActivityIdControl` at `0x18004fd44`
- `ntdll!EtwEventActivityIdControl` at `0x18004fd76`
- `ntdll!EtwEventActivityIdControl` at `0x18004fd44`
- `ntdll!EtwEventActivityIdControl` at `0x18004fd76`
- `ntdll!EtwEventWrite` at `0x18004fd57`
- `ntdll!EtwEventWrite` at `0x18004fd57`

## string_xrefs

- `0x18004fd8d`: `EventWrite error`

## pseudocode

```c
__int64 __fastcall EventManager::EvtReport(
        EventManager *this,
        const struct _EVENT_DESCRIPTOR *a2,
        const unsigned __int16 *a3,
        const struct _GUID *a4)
{
  EventManager *v4; // rsi
  signed int v9; // eax
  signed int v10; // edi
  EventManager *v11; // rcx
  _QWORD v12[2]; // [rsp+20h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+30h] [rbp-30h] BYREF
  const struct _GUID *v14; // [rsp+40h] [rbp-20h]
  __int64 v15; // [rsp+48h] [rbp-18h]

  v4 = g_pEventManager;
  if ( !*(_QWORD *)g_pEventManager )
    return 1;
  if ( !(unsigned __int8)EtwEventEnabled(*(_QWORD *)g_pEventManager, a2) )
    return 0;
  CreateDataDescriptor(&v13, a3);
  v14 = a4;
  v15 = 16;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v4 + 8));
  EtwEventActivityIdControl(2, a4);
  v9 = EtwEventWrite(*(_QWORD *)v4, a2, 2, &v13);
  v12[0] = 0;
  v12[1] = 0;
  v10 = v9;
  EtwEventActivityIdControl(2, v12);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v4 + 8));
  if ( !v10 )
    return 0;
  EventManager::LogIt(v11, L"EventWrite error", v10);
  if ( v10 > 0 )
    return (unsigned __int16)v10 | 0x80070000;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18004fccc  push    rbp
0x18004fcce  push    rbx
0x18004fccf  push    rsi
0x18004fcd0  push    rdi
0x18004fcd1  push    r14
0x18004fcd3  mov     rbp, rsp
0x18004fcd6  sub     rsp, 60h
0x18004fcda  mov     rax, cs:__security_cookie
0x18004fce1  xor     rax, rsp
0x18004fce4  mov     [rbp+var_10], rax
0x18004fce8  mov     rsi, cs:?g_pEventManager@@3PEAVEventManager@@EA; EventManager * g_pEventManager
0x18004fcef  mov     r14, r9
0x18004fcf2  mov     rbx, r8
0x18004fcf5  mov     rdi, rdx
0x18004fcf8  mov     rcx, [rsi]
0x18004fcfb  test    rcx, rcx
0x18004fcfe  jnz     short loc_18004FD08
0x18004fd00  lea     eax, [rcx+1]
0x18004fd03  jmp     loc_18004FDAC
0x18004fd08  call    cs:__imp_EtwEventEnabled
0x18004fd0e  test    al, al
0x18004fd10  jz      loc_18004FDAA
0x18004fd16  mov     rdx, rbx; unsigned __int16 *
0x18004fd19  lea     rcx, [rbp+var_30]; struct _EVENT_DATA_DESCRIPTOR *
0x18004fd1d  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x18004fd22  lea     rcx, [rsi+8]; lpCriticalSection
0x18004fd26  mov     [rbp+var_20], r14
0x18004fd2a  mov     [rbp+var_18], 10h
0x18004fd32  call    cs:__imp_EnterCriticalSection
0x18004fd38  mov     rdx, r14
0x18004fd3b  mov     r14d, 2
0x18004fd41  mov     ecx, r14d
0x18004fd44  call    cs:__imp_EtwEventActivityIdControl
0x18004fd4a  mov     rcx, [rsi]
0x18004fd4d  lea     r9, [rbp+var_30]
0x18004fd51  mov     r8d, r14d
0x18004fd54  mov     rdx, rdi
0x18004fd57  call    cs:__imp_EtwEventWrite
0x18004fd5d  lea     rdx, [rbp+var_40]
0x18004fd61  mov     [rbp+var_40], 0
0x18004fd69  mov     ecx, r14d
0x18004fd6c  mov     [rbp+var_38], 0
0x18004fd74  mov     edi, eax
0x18004fd76  call    cs:__imp_EtwEventActivityIdControl
0x18004fd7c  lea     rcx, [rsi+8]; lpCriticalSection
0x18004fd80  call    cs:__imp_LeaveCriticalSection
0x18004fd86  test    edi, edi
0x18004fd88  jz      short loc_18004FDAA
0x18004fd8a  mov     r8d, edi; unsigned int
0x18004fd8d  lea     rdx, aEventwriteErro; "EventWrite error"
0x18004fd94  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x18004fd99  test    edi, edi
0x18004fd9b  jle     short loc_18004FDA6
0x18004fd9d  movzx   edi, di
0x18004fda0  or      edi, 80070000h
0x18004fda6  mov     eax, edi
0x18004fda8  jmp     short loc_18004FDAC
0x18004fdaa  xor     eax, eax
0x18004fdac  mov     rcx, [rbp+var_10]
0x18004fdb0  xor     rcx, rsp; StackCookie
0x18004fdb3  call    __security_check_cookie
0x18004fdb8  add     rsp, 60h
0x18004fdbc  pop     r14
0x18004fdbe  pop     rdi
0x18004fdbf  pop     rsi
0x18004fdc0  pop     rbx
0x18004fdc1  pop     rbp
0x18004fdc2  retn
```
