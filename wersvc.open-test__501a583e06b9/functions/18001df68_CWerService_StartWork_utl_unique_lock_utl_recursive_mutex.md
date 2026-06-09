# CWerService::_StartWork(utl::unique_lock<utl::recursive_mutex> &)

- ea: `0x18001df68`
- end: `0x18001e04b`
- name: `?_StartWork@CWerService@@AEAAJAEAV?$unique_lock@Vrecursive_mutex@utl@@@utl@@@Z`
- size: `227`
- prototype: `__int64 __fastcall(CWerService *this)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800181f8`
- `0x180018700`

## callees

- `0x180006a80`
- `0x180011ef8`
- `0x18001d9e8`
- `0x18001df68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dff0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dff0`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18001dfe6`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18001dfe6`

## pseudocode

```c
__int64 __fastcall CWerService::_StartWork(CWerService *this, __int64 a2, __int64 a3, __int64 a4)
{
  int started; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  signed int LastError; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids);
  started = CWerService::_StartLpcServer(this, a2, a3, a4);
  if ( started >= 0 )
  {
    if ( !TrySubmitThreadpoolCallback(
            CWerService::StaticDelayedStartWorkItem,
            this,
            (PTP_CALLBACK_ENVIRON)((char *)this + 232)) )
    {
      LastError = GetLastError();
      started = LastError;
      if ( LastError > 0 )
        started = (unsigned __int16)LastError | 0x80070000;
      if ( started >= 0 )
        started = -2147467259;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 61;
        goto LABEL_16;
      }
    }
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 60;
LABEL_16:
      WPP_SF_d(v7[2], v8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids, (unsigned int)started);
    }
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18001df68  mov     [rsp+arg_0], rbx
0x18001df6d  mov     [rsp+arg_8], rsi
0x18001df72  push    rdi
0x18001df73  sub     rsp, 20h
0x18001df77  mov     rbx, rdx
0x18001df7a  mov     rdi, rcx
0x18001df7d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001df84  lea     rsi, WPP_GLOBAL_Control
0x18001df8b  cmp     rcx, rsi
0x18001df8e  jz      short loc_18001DFAB
0x18001df90  test    byte ptr [rcx+1Ch], 4
0x18001df94  jz      short loc_18001DFAB
0x18001df96  mov     rcx, [rcx+10h]
0x18001df9a  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001dfa1  mov     edx, 3Bh ; ';'
0x18001dfa6  call    WPP_SF_
0x18001dfab  mov     rdx, rbx
0x18001dfae  mov     rcx, rdi; this
0x18001dfb1  call    ?_StartLpcServer@CWerService@@AEAAJAEAV?$unique_lock@Vrecursive_mutex@utl@@@utl@@@Z; CWerService::_StartLpcServer(utl::unique_lock<utl::recursive_mutex> &)
0x18001dfb6  mov     ebx, eax
0x18001dfb8  test    eax, eax
0x18001dfba  jns     short loc_18001DFD5
0x18001dfbc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dfc3  cmp     rcx, rsi
0x18001dfc6  jz      short loc_18001E039
0x18001dfc8  test    byte ptr [rcx+1Ch], 1
0x18001dfcc  jz      short loc_18001E039
0x18001dfce  mov     edx, 3Ch ; '<'
0x18001dfd3  jmp     short loc_18001E026
0x18001dfd5  lea     r8, [rdi+0E8h]; pcbe
0x18001dfdc  mov     rdx, rdi; pv
0x18001dfdf  lea     rcx, ?StaticDelayedStartWorkItem@CWerService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x18001dfe6  call    cs:__imp_TrySubmitThreadpoolCallback
0x18001dfec  test    eax, eax
0x18001dfee  jnz     short loc_18001E039
0x18001dff0  call    cs:__imp_GetLastError
0x18001dff6  mov     ebx, eax
0x18001dff8  test    eax, eax
0x18001dffa  jle     short loc_18001E005
0x18001dffc  movzx   ebx, ax
0x18001dfff  or      ebx, 80070000h
0x18001e005  test    ebx, ebx
0x18001e007  mov     eax, 80004005h
0x18001e00c  cmovns  ebx, eax
0x18001e00f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e016  cmp     rcx, rsi
0x18001e019  jz      short loc_18001E039
0x18001e01b  test    byte ptr [rcx+1Ch], 1
0x18001e01f  jz      short loc_18001E039
0x18001e021  mov     edx, 3Dh ; '='
0x18001e026  mov     rcx, [rcx+10h]
0x18001e02a  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001e031  mov     r9d, ebx
0x18001e034  call    WPP_SF_d
0x18001e039  mov     rsi, [rsp+28h+arg_8]
0x18001e03e  mov     eax, ebx
0x18001e040  mov     rbx, [rsp+28h+arg_0]
0x18001e045  add     rsp, 20h
0x18001e049  pop     rdi
0x18001e04a  retn
```
