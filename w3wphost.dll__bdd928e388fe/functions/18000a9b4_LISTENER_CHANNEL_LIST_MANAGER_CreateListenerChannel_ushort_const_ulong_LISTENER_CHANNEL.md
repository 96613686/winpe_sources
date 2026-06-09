# LISTENER_CHANNEL_LIST_MANAGER::CreateListenerChannel(ushort const *,ulong,LISTENER_CHANNEL * *)

- ea: `0x18000a9b4`
- end: `0x18000ab26`
- name: `?CreateListenerChannel@LISTENER_CHANNEL_LIST_MANAGER@@AEAAJPEBGKPEAPEAVLISTENER_CHANNEL@@@Z`
- size: `370`
- prototype: `__int64 __fastcall(LISTENER_CHANNEL_LIST_MANAGER *__hidden this, const unsigned __int16 *, unsigned int, struct LISTENER_CHANNEL **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000abd0`

## callees

- `0x180001f68`
- `0x180009e24`
- `0x180009ef0`
- `0x18000a9b4`
- `0x18000d010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18000aa7e`
- `iisutil!PuDbgPrint` at `0x18000ab13`
- `iisutil!PuDbgPrint` at `0x18000aa7e`
- `iisutil!PuDbgPrint` at `0x18000ab13`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000a9f9`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000a9f9`

## string_xrefs

- `0x18000aa77`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\listener_channel_list_manager.cxx`
- `0x18000ab06`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3wphost\listener_channel_list_manager.cxx`
- `0x18000aa65`: `LISTENER_CHANNEL_LIST_MANAGER::CreateListenerChannel`
- `0x18000aaf8`: `LISTENER_CHANNEL_LIST_MANAGER::CreateListenerChannel`

## pseudocode

```c
__int64 __fastcall LISTENER_CHANNEL_LIST_MANAGER::CreateListenerChannel(
        LISTENER_CHANNEL_LIST_MANAGER *this,
        const unsigned __int16 *a2,
        int a3,
        struct LISTENER_CHANNEL **a4)
{
  LISTENER_CHANNEL *v8; // rax
  LISTENER_CHANNEL *v9; // rax
  LISTENER_CHANNEL *v10; // rdi
  int v11; // ebx
  LISTENER_CHANNEL_WORKITEM *v12; // rax
  LISTENER_CHANNEL_WORKITEM *v13; // rbx
  _QWORD *v14; // rcx
  __int64 v15; // rdx

  v8 = (LISTENER_CHANNEL *)operator new(0x140u);
  if ( v8 && (v9 = LISTENER_CHANNEL::LISTENER_CHANNEL(v8), (v10 = v9) != 0) )
  {
    v11 = STRU::Copy((LISTENER_CHANNEL *)((char *)v9 + 16), a2);
    if ( v11 < 0 )
    {
LABEL_9:
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\listener_channel_list_manager.cxx",
          642,
          "LISTENER_CHANNEL_LIST_MANAGER::CreateListenerChannel",
          "Failed initializing the ListenerChannelContext hr = %x \r\n");
      (*(void (__fastcall **)(LISTENER_CHANNEL *))(*(_QWORD *)v10 + 8LL))(v10);
      return (unsigned int)v11;
    }
    v12 = (LISTENER_CHANNEL_WORKITEM *)operator new(0x38u);
    v13 = v12;
    if ( v12 )
    {
      LISTENER_CHANNEL_WORKITEM::LISTENER_CHANNEL_WORKITEM(v12, 0, 0);
      *((_DWORD *)v13 + 12) = 0;
      *(_QWORD *)v13 = &LISTENER_CHANNEL_STOP_WORKITEM::`vftable';
    }
    else
    {
      v13 = 0;
    }
    *((_QWORD *)v10 + 39) = v13;
    if ( !v13 )
    {
      v11 = -2147024888;
      goto LABEL_9;
    }
    *((_DWORD *)v10 + 18) = a3;
    *((_DWORD *)v10 + 66) = 1;
    v14 = (_QWORD *)((char *)this + 8);
    v15 = *((_QWORD *)this + 1);
    if ( *(LISTENER_CHANNEL_LIST_MANAGER **)(v15 + 8) != (LISTENER_CHANNEL_LIST_MANAGER *)((char *)this + 8) )
      __fastfail(3u);
    *a4 = v10;
    *((_QWORD *)v10 + 31) = v15;
    v11 = 0;
    *((_QWORD *)v10 + 32) = v14;
    *(_QWORD *)(v15 + 8) = (char *)v10 + 248;
    *v14 = (char *)v10 + 248;
  }
  else
  {
    v11 = -2147024882;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3wphost\\listener_channel_list_manager.cxx",
        627,
        "LISTENER_CHANNEL_LIST_MANAGER::CreateListenerChannel",
        "Out of memory creating a listenerChannel host hr = %x \r\n");
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000a9b4  push    rbx
0x18000a9b6  push    rbp
0x18000a9b7  push    rsi
0x18000a9b8  push    rdi
0x18000a9b9  push    r14
0x18000a9bb  sub     rsp, 30h
0x18000a9bf  mov     rbp, rcx
0x18000a9c2  mov     r14, r9
0x18000a9c5  mov     ecx, 140h; Size
0x18000a9ca  mov     esi, r8d
0x18000a9cd  mov     rbx, rdx
0x18000a9d0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a9d5  test    rax, rax
0x18000a9d8  jz      loc_18000AADA
0x18000a9de  mov     rcx, rax; this
0x18000a9e1  call    ??0LISTENER_CHANNEL@@QEAA@XZ; LISTENER_CHANNEL::LISTENER_CHANNEL(void)
0x18000a9e6  mov     rdi, rax
0x18000a9e9  test    rax, rax
0x18000a9ec  jz      loc_18000AADA
0x18000a9f2  lea     rcx, [rax+10h]
0x18000a9f6  mov     rdx, rbx
0x18000a9f9  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000a9ff  mov     ebx, eax
0x18000aa01  test    eax, eax
0x18000aa03  js      short loc_18000AA4A
0x18000aa05  mov     ecx, 38h ; '8'; Size
0x18000aa0a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000aa0f  mov     rbx, rax
0x18000aa12  test    rax, rax
0x18000aa15  jz      short loc_18000AA37
0x18000aa17  xor     r8d, r8d; int
0x18000aa1a  xor     edx, edx; struct LISTENER_CHANNEL *
0x18000aa1c  mov     rcx, rax; this
0x18000aa1f  call    ??0LISTENER_CHANNEL_WORKITEM@@QEAA@PEAVLISTENER_CHANNEL@@H@Z; LISTENER_CHANNEL_WORKITEM::LISTENER_CHANNEL_WORKITEM(LISTENER_CHANNEL *,int)
0x18000aa24  lea     rax, ??_7LISTENER_CHANNEL_STOP_WORKITEM@@6B@; const LISTENER_CHANNEL_STOP_WORKITEM::`vftable'
0x18000aa2b  mov     dword ptr [rbx+30h], 0
0x18000aa32  mov     [rbx], rax
0x18000aa35  jmp     short loc_18000AA39
0x18000aa37  xor     ebx, ebx
0x18000aa39  mov     [rdi+138h], rbx
0x18000aa40  test    rbx, rbx
0x18000aa43  jnz     short loc_18000AA9D
0x18000aa45  mov     ebx, 80070008h
0x18000aa4a  test    byte ptr cs:g_dwDebugFlags, 3
0x18000aa51  jz      short loc_18000AA84
0x18000aa53  mov     rcx, cs:g_pDebug
0x18000aa5a  lea     rax, aFailedInitiali; "Failed initializing the ListenerChannel"...
0x18000aa61  mov     [rsp+58h+var_30], ebx
0x18000aa65  lea     r9, aListenerChanne_2; "LISTENER_CHANNEL_LIST_MANAGER::CreateLi"...
0x18000aa6c  mov     r8d, 282h
0x18000aa72  mov     [rsp+58h+var_38], rax
0x18000aa77  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000aa7e  call    cs:__imp_PuDbgPrint
0x18000aa84  test    ebx, ebx
0x18000aa86  jns     loc_18000AB19
0x18000aa8c  mov     rax, [rdi]
0x18000aa8f  mov     rcx, rdi
0x18000aa92  mov     rax, [rax+8]
0x18000aa96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa9b  jmp     short loc_18000AB19
0x18000aa9d  mov     [rdi+48h], esi
0x18000aaa0  mov     dword ptr [rdi+108h], 1
0x18000aaaa  lea     rcx, [rbp+8]
0x18000aaae  mov     rdx, [rcx]
0x18000aab1  cmp     [rdx+8], rcx
0x18000aab5  jz      short loc_18000AABE
0x18000aab7  mov     ecx, 3
0x18000aabc  int     29h; Win8: RtlFailFast(ecx)
0x18000aabe  lea     rax, [rdi+0F8h]
0x18000aac5  mov     [r14], rdi
0x18000aac8  mov     [rax], rdx
0x18000aacb  xor     ebx, ebx
0x18000aacd  mov     [rax+8], rcx
0x18000aad1  mov     [rdx+8], rax
0x18000aad5  mov     [rcx], rax
0x18000aad8  jmp     short loc_18000AB19
0x18000aada  test    byte ptr cs:g_dwDebugFlags, 3
0x18000aae1  mov     ebx, 8007000Eh
0x18000aae6  jz      short loc_18000AB19
0x18000aae8  lea     rcx, aOutOfMemoryCre; "Out of memory creating a listenerChanne"...
0x18000aaef  mov     [rsp+58h+var_30], ebx
0x18000aaf3  mov     [rsp+58h+var_38], rcx
0x18000aaf8  lea     r9, aListenerChanne_2; "LISTENER_CHANNEL_LIST_MANAGER::CreateLi"...
0x18000aaff  mov     rcx, cs:g_pDebug
0x18000ab06  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000ab0d  mov     r8d, 273h
0x18000ab13  call    cs:__imp_PuDbgPrint
0x18000ab19  mov     eax, ebx
0x18000ab1b  add     rsp, 30h
0x18000ab1f  pop     r14
0x18000ab21  pop     rdi
0x18000ab22  pop     rsi
0x18000ab23  pop     rbp
0x18000ab24  pop     rbx
0x18000ab25  retn
```
