# Radio::CRadioSwitchManager::_StartHidReaderThread(void)

- ea: `0x18002af7c`
- end: `0x18002b13a`
- name: `?_StartHidReaderThread@CRadioSwitchManager@Radio@@AEAAXXZ`
- size: `446`
- prototype: `void __fastcall(DWORD *this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180014de0`
- `0x18002ac70`

## callees

- `0x18002af7c`
- `0x18002b4e8`
- `0x180032c6a`
- `0x180032c90`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002b005`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002b005`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002afc1`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002afc1`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x18002b0e8`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x18002b0e8`

## string_xrefs

- `0x18002affe`: `shsvcs.dll`

## pseudocode

```c
void __fastcall Radio::CRadioSwitchManager::_StartHidReaderThread(DWORD *this)
{
  HANDLE Thread; // rax
  HMODULE ModuleHandleW; // rax
  _QWORD v4[3]; // [rsp+30h] [rbp-1B8h] BYREF
  _BYTE v5[392]; // [rsp+48h] [rbp-1A0h] BYREF

  Thread = CreateThread(0, 0, Radio::CRadioSwitchManager::s_HidReaderThread, this, 0, this + 316);
  *((_QWORD *)this + 159) = Thread;
  if ( !Thread
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26);
  }
  ModuleHandleW = GetModuleHandleW(L"shsvcs.dll");
  if ( ModuleHandleW )
  {
    this[324] = 3;
    *((_QWORD *)this + 163) = 0;
    *((_QWORD *)this + 164) = 0;
    *((_QWORD *)this + 165) = 0;
    *((_QWORD *)this + 167) = 0;
    *((_QWORD *)this + 168) = 0;
    this[338] = 0;
    this[339] = 1;
    this[340] = 72;
    *((_QWORD *)this + 166) = ModuleHandleW;
    *((_BYTE *)this + 1288) = 1;
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27);
  }
  memset_0(v5, 0, sizeof(v5));
  v4[2] = *((_QWORD *)this + 6);
  v4[0] = 416;
  v4[1] = 1;
  if ( (unsigned int)CM_Register_Notification(v4, this, &Radio::CRadioSwitchManager::s_HidEventCallback, this + 344)
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28);
  }
}

```

## disassembly

```asm
0x18002af7c  mov     [rsp+arg_8], rbx
0x18002af81  push    r14
0x18002af83  sub     rsp, 1E0h
0x18002af8a  mov     rax, cs:__security_cookie
0x18002af91  xor     rax, rsp
0x18002af94  mov     [rsp+1E8h+var_18], rax
0x18002af9c  lea     rax, [rcx+4F0h]
0x18002afa3  mov     rbx, rcx
0x18002afa6  mov     r9, rcx; lpParameter
0x18002afa9  mov     [rsp+1E8h+lpThreadId], rax; lpThreadId
0x18002afae  lea     r8, ?s_HidReaderThread@CRadioSwitchManager@Radio@@CAKPEAV12@@Z; lpStartAddress
0x18002afb5  mov     [rsp+1E8h+dwCreationFlags], 0; dwCreationFlags
0x18002afbd  xor     edx, edx; dwStackSize
0x18002afbf  xor     ecx, ecx; lpThreadAttributes
0x18002afc1  call    cs:__imp_CreateThread
0x18002afc7  mov     [rbx+4F8h], rax
0x18002afce  lea     r14, WPP_GLOBAL_Control
0x18002afd5  test    rax, rax
0x18002afd8  jnz     short loc_18002AFFE
0x18002afda  mov     rcx, cs:WPP_GLOBAL_Control
0x18002afe1  cmp     rcx, r14
0x18002afe4  jz      short loc_18002AFFE
0x18002afe6  test    byte ptr [rcx+1Ch], 4
0x18002afea  jz      short loc_18002AFFE
0x18002afec  cmp     byte ptr [rcx+19h], 2
0x18002aff0  jb      short loc_18002AFFE
0x18002aff2  mov     rcx, [rcx+10h]
0x18002aff6  lea     edx, [rax+1Ah]
0x18002aff9  call    WPP_SF_
0x18002affe  lea     rcx, aShsvcsDll_0; "shsvcs.dll"
0x18002b005  call    cs:__imp_GetModuleHandleW
0x18002b00b  test    rax, rax
0x18002b00e  jz      short loc_18002B07F
0x18002b010  mov     dword ptr [rbx+510h], 3
0x18002b01a  mov     qword ptr [rbx+518h], 0
0x18002b025  mov     qword ptr [rbx+520h], 0
0x18002b030  mov     qword ptr [rbx+528h], 0
0x18002b03b  mov     qword ptr [rbx+538h], 0
0x18002b046  mov     qword ptr [rbx+540h], 0
0x18002b051  mov     dword ptr [rbx+548h], 0
0x18002b05b  mov     dword ptr [rbx+54Ch], 1
0x18002b065  mov     dword ptr [rbx+550h], 48h ; 'H'
0x18002b06f  mov     [rbx+530h], rax
0x18002b076  mov     byte ptr [rbx+508h], 1
0x18002b07d  jmp     short loc_18002B0A5
0x18002b07f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b086  cmp     rcx, r14
0x18002b089  jz      short loc_18002B0A5
0x18002b08b  test    byte ptr [rcx+1Ch], 4
0x18002b08f  jz      short loc_18002B0A5
0x18002b091  cmp     byte ptr [rcx+19h], 2
0x18002b095  jb      short loc_18002B0A5
0x18002b097  mov     rcx, [rcx+10h]
0x18002b09b  mov     edx, 1Bh
0x18002b0a0  call    WPP_SF_
0x18002b0a5  xor     edx, edx; Val
0x18002b0a7  lea     rcx, [rsp+1E8h+var_1A0]; void *
0x18002b0ac  mov     r8d, 188h; Size
0x18002b0b2  call    memset_0
0x18002b0b7  mov     rax, [rbx+30h]
0x18002b0bb  lea     r9, [rbx+560h]
0x18002b0c2  lea     r8, ?s_HidEventCallback@CRadioSwitchManager@Radio@@CAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z; Radio::CRadioSwitchManager::s_HidEventCallback(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)
0x18002b0c9  mov     [rsp+1E8h+var_1A8], rax
0x18002b0ce  mov     rdx, rbx
0x18002b0d1  mov     [rsp+1E8h+var_1B8], 1A0h
0x18002b0da  lea     rcx, [rsp+1E8h+var_1B8]
0x18002b0df  mov     [rsp+1E8h+var_1B0], 1
0x18002b0e8  call    cs:__imp_CM_Register_Notification
0x18002b0ee  test    eax, eax
0x18002b0f0  jz      short loc_18002B118
0x18002b0f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b0f9  cmp     rcx, r14
0x18002b0fc  jz      short loc_18002B118
0x18002b0fe  test    byte ptr [rcx+1Ch], 4
0x18002b102  jz      short loc_18002B118
0x18002b104  cmp     byte ptr [rcx+19h], 2
0x18002b108  jb      short loc_18002B118
0x18002b10a  mov     rcx, [rcx+10h]
0x18002b10e  mov     edx, 1Ch
0x18002b113  call    WPP_SF_
0x18002b118  mov     rcx, [rsp+1E8h+var_18]
0x18002b120  xor     rcx, rsp; StackCookie
0x18002b123  call    __security_check_cookie
0x18002b128  mov     rbx, [rsp+1E8h+arg_8]
0x18002b130  add     rsp, 1E0h
0x18002b137  pop     r14
0x18002b139  retn
```
