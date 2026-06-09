# Radio::CRadioSwitchManager::_StopHidReaderThread(void)

- ea: `0x18002b140`
- end: `0x18002b2ec`
- name: `?_StopHidReaderThread@CRadioSwitchManager@Radio@@AEAAXXZ`
- size: `428`
- prototype: `void __fastcall(Radio::CRadioSwitchManager *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18002abac`
- `0x18002add0`
- `0x18002aee0`

## callees

- `0x18002b140`
- `0x18002b4e8`
- `0x180032c6a`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002b228`
- `msvcrt!_wcsicmp` at `0x18002b228`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002b161`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002b161`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002b1a9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002b1a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b1b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b1b6`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18002b1e5`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18002b1e5`
- `Rmapi!__imp_RadioHidDeviceFree` at `0x18002b238`
- `Rmapi!__imp_RadioHidDeviceFree` at `0x18002b278`
- `Rmapi!__imp_RadioHidDeviceFree` at `0x18002b238`
- `Rmapi!__imp_RadioHidDeviceFree` at `0x18002b278`

## pseudocode

```c
void __fastcall Radio::CRadioSwitchManager::_StopHidReaderThread(Radio::CRadioSwitchManager *this)
{
  BOOL v2; // edi
  void *v3; // rcx
  void *v4; // rcx
  _QWORD *v5; // rcx

  v2 = 0;
  v3 = (void *)*((_QWORD *)this + 160);
  if ( v3 )
    v2 = SetEvent(v3);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31);
  }
  v4 = (void *)*((_QWORD *)this + 159);
  if ( v4 )
  {
    if ( v2 )
      WaitForSingleObject(v4, 0xFFFFFFFF);
    CloseHandle(*((HANDLE *)this + 159));
    *((_QWORD *)this + 159) = 0;
  }
  if ( *((_BYTE *)this + 1288) == 1
    && !TrySubmitThreadpoolCallback(
          Radio::DeferredQueryRemoveUnregister,
          *((PVOID *)this + 172),
          (PTP_CALLBACK_ENVIRON)this + 18)
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32);
  }
  if ( *((_BYTE *)this + 41) )
  {
    if ( !_wcsicmp((const wchar_t *)this + 28, (const wchar_t *)this + 332) )
    {
      *((_BYTE *)this + 41) = 0;
      RadioHidDeviceFree((char *)this + 656);
      memset_0((char *)this + 656, 0, 0x260u);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33);
      }
    }
  }
  RadioHidDeviceFree((char *)this + 48);
  memset_0((char *)this + 48, 0, 0x260u);
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34);
      v5 = WPP_GLOBAL_Control;
    }
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 4) != 0 && *((_BYTE *)v5 + 25) >= 4u )
      WPP_SF_(v5[2], 35);
  }
}

```

## disassembly

```asm
0x18002b140  mov     [rsp+arg_0], rbx
0x18002b145  mov     [rsp+arg_8], rdi
0x18002b14a  push    r14
0x18002b14c  sub     rsp, 20h
0x18002b150  mov     rbx, rcx
0x18002b153  xor     edi, edi
0x18002b155  mov     rcx, [rcx+500h]; hEvent
0x18002b15c  test    rcx, rcx
0x18002b15f  jz      short loc_18002B169
0x18002b161  call    cs:__imp_SetEvent
0x18002b167  mov     edi, eax
0x18002b169  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b170  lea     r14, WPP_GLOBAL_Control
0x18002b177  cmp     rcx, r14
0x18002b17a  jz      short loc_18002B196
0x18002b17c  test    byte ptr [rcx+1Ch], 4
0x18002b180  jz      short loc_18002B196
0x18002b182  cmp     byte ptr [rcx+19h], 4
0x18002b186  jb      short loc_18002B196
0x18002b188  mov     rcx, [rcx+10h]
0x18002b18c  mov     edx, 1Fh
0x18002b191  call    WPP_SF_
0x18002b196  mov     rcx, [rbx+4F8h]; hHandle
0x18002b19d  test    rcx, rcx
0x18002b1a0  jz      short loc_18002B1C7
0x18002b1a2  test    edi, edi
0x18002b1a4  jz      short loc_18002B1AF
0x18002b1a6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002b1a9  call    cs:__imp_WaitForSingleObject
0x18002b1af  mov     rcx, [rbx+4F8h]; hObject
0x18002b1b6  call    cs:__imp_CloseHandle
0x18002b1bc  mov     qword ptr [rbx+4F8h], 0
0x18002b1c7  cmp     byte ptr [rbx+508h], 1
0x18002b1ce  jnz     short loc_18002B213
0x18002b1d0  mov     rdx, [rbx+560h]; pv
0x18002b1d7  lea     r8, [rbx+510h]; pcbe
0x18002b1de  lea     rcx, ?DeferredQueryRemoveUnregister@Radio@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x18002b1e5  call    cs:__imp_TrySubmitThreadpoolCallback
0x18002b1eb  test    eax, eax
0x18002b1ed  jnz     short loc_18002B213
0x18002b1ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b1f6  cmp     rcx, r14
0x18002b1f9  jz      short loc_18002B213
0x18002b1fb  test    byte ptr [rcx+1Ch], 4
0x18002b1ff  jz      short loc_18002B213
0x18002b201  cmp     byte ptr [rcx+19h], 2
0x18002b205  jb      short loc_18002B213
0x18002b207  mov     rcx, [rcx+10h]
0x18002b20b  lea     edx, [rax+20h]
0x18002b20e  call    WPP_SF_
0x18002b213  cmp     byte ptr [rbx+29h], 0
0x18002b217  jz      short loc_18002B274
0x18002b219  lea     rdi, [rbx+290h]
0x18002b220  lea     rdx, [rdi+8]; String2
0x18002b224  lea     rcx, [rbx+38h]; String1
0x18002b228  call    cs:__imp__wcsicmp
0x18002b22e  test    eax, eax
0x18002b230  jnz     short loc_18002B274
0x18002b232  mov     rcx, rdi
0x18002b235  mov     [rbx+29h], al
0x18002b238  call    cs:__imp_RadioHidDeviceFree
0x18002b23e  xor     edx, edx; Val
0x18002b240  mov     r8d, 260h; Size
0x18002b246  mov     rcx, rdi; void *
0x18002b249  call    memset_0
0x18002b24e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b255  cmp     rcx, r14
0x18002b258  jz      short loc_18002B274
0x18002b25a  test    byte ptr [rcx+1Ch], 4
0x18002b25e  jz      short loc_18002B274
0x18002b260  cmp     byte ptr [rcx+19h], 4
0x18002b264  jb      short loc_18002B274
0x18002b266  mov     rcx, [rcx+10h]
0x18002b26a  mov     edx, 21h ; '!'
0x18002b26f  call    WPP_SF_
0x18002b274  lea     rcx, [rbx+30h]
0x18002b278  call    cs:__imp_RadioHidDeviceFree
0x18002b27e  xor     edx, edx; Val
0x18002b280  lea     rcx, [rbx+30h]; void *
0x18002b284  mov     r8d, 260h; Size
0x18002b28a  call    memset_0
0x18002b28f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b296  cmp     rcx, r14
0x18002b299  jz      short loc_18002B2DB
0x18002b29b  test    byte ptr [rcx+1Ch], 4
0x18002b29f  jz      short loc_18002B2BC
0x18002b2a1  cmp     byte ptr [rcx+19h], 4
0x18002b2a5  jb      short loc_18002B2BC
0x18002b2a7  mov     rcx, [rcx+10h]
0x18002b2ab  mov     edx, 22h ; '"'
0x18002b2b0  call    WPP_SF_
0x18002b2b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b2bc  cmp     rcx, r14
0x18002b2bf  jz      short loc_18002B2DB
0x18002b2c1  test    byte ptr [rcx+1Ch], 4
0x18002b2c5  jz      short loc_18002B2DB
0x18002b2c7  cmp     byte ptr [rcx+19h], 4
0x18002b2cb  jb      short loc_18002B2DB
0x18002b2cd  mov     rcx, [rcx+10h]
0x18002b2d1  mov     edx, 23h ; '#'
0x18002b2d6  call    WPP_SF_
0x18002b2db  mov     rbx, [rsp+28h+arg_0]
0x18002b2e0  mov     rdi, [rsp+28h+arg_8]
0x18002b2e5  add     rsp, 20h
0x18002b2e9  pop     r14
0x18002b2eb  retn
```
