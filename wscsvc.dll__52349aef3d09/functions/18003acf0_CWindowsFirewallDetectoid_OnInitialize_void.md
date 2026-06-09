# CWindowsFirewallDetectoid::OnInitialize(void)

- ea: `0x18003acf0`
- end: `0x18003ad60`
- name: `?OnInitialize@CWindowsFirewallDetectoid@@MEAAJXZ`
- size: `112`
- prototype: `__int64 __fastcall(CWindowsFirewallDetectoid *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18003acf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003ad0e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003ad0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ad1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ad1d`
- `FirewallAPI!FWChangeNotificationCreate` at `0x18003ad50`
- `FirewallAPI!FWChangeNotificationCreate` at `0x18003ad50`

## pseudocode

```c
__int64 __fastcall CWindowsFirewallDetectoid::OnInitialize(CWindowsFirewallDetectoid *this)
{
  HANDLE EventW; // rax
  signed int LastError; // eax
  unsigned int v4; // ebx
  __int64 result; // rax

  *((_DWORD *)this + 10) = 2;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 11) = EventW;
  if ( EventW )
  {
    v4 = 0;
    LastError = FWChangeNotificationCreate(EventW, (char *)this + 96);
    if ( !LastError )
      goto LABEL_4;
    if ( LastError <= 0 )
    {
      v4 = LastError;
      goto LABEL_4;
    }
    goto LABEL_3;
  }
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
LABEL_3:
    v4 = (unsigned __int16)LastError | 0x80070000;
LABEL_4:
  result = v4;
  *((_QWORD *)this + 8) = 0;
  return result;
}

```

## disassembly

```asm
0x18003acf0  mov     [rsp+arg_0], rbx
0x18003acf5  push    rdi
0x18003acf6  sub     rsp, 20h
0x18003acfa  mov     rdi, rcx
0x18003acfd  mov     dword ptr [rcx+28h], 2
0x18003ad04  xor     ecx, ecx; lpEventAttributes
0x18003ad06  xor     r9d, r9d; lpName
0x18003ad09  xor     r8d, r8d; bInitialState
0x18003ad0c  xor     edx, edx; bManualReset
0x18003ad0e  call    cs:__imp_CreateEventW
0x18003ad14  mov     [rdi+58h], rax
0x18003ad18  test    rax, rax
0x18003ad1b  jnz     short loc_18003AD47
0x18003ad1d  call    cs:__imp_GetLastError
0x18003ad23  mov     ebx, eax
0x18003ad25  test    eax, eax
0x18003ad27  jle     short loc_18003AD32
0x18003ad29  movzx   ebx, ax
0x18003ad2c  or      ebx, 80070000h
0x18003ad32  mov     eax, ebx
0x18003ad34  mov     qword ptr [rdi+40h], 0
0x18003ad3c  mov     rbx, [rsp+28h+arg_0]
0x18003ad41  add     rsp, 20h
0x18003ad45  pop     rdi
0x18003ad46  retn
0x18003ad47  lea     rdx, [rdi+60h]
0x18003ad4b  mov     rcx, rax
0x18003ad4e  xor     ebx, ebx
0x18003ad50  call    cs:__imp_FWChangeNotificationCreate
0x18003ad56  test    eax, eax
0x18003ad58  jz      short loc_18003AD32
0x18003ad5a  jg      short loc_18003AD29
0x18003ad5c  mov     ebx, eax
0x18003ad5e  jmp     short loc_18003AD32
```
