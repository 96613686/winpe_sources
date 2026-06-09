# CHMESharedLibraryMonitor::Initialize(void)

- ea: `0x14008af50`
- end: `0x14008b019`
- name: `?Initialize@CHMESharedLibraryMonitor@@QEAAJXZ`
- size: `201`
- prototype: `__int64 __fastcall(CHMESharedLibraryMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14004c6ac`

## callees

- `0x140032eec`
- `0x1400350e4`
- `0x140040890`
- `0x14008af50`
- `0x14008bf4c`

## import_xrefs

- `KERNEL32!CreateThread` at `0x14008afeb`
- `KERNEL32!CreateThread` at `0x14008afeb`
- `KERNEL32!CreateEventW` at `0x14008af9c`
- `KERNEL32!CreateEventW` at `0x14008af9c`

## pseudocode

```c
__int64 __fastcall CHMESharedLibraryMonitor::Initialize(CHMESharedLibraryMonitor *this)
{
  int Registry; // ebx
  int v3; // eax
  HANDLE EventW; // rax
  __int64 v5; // r8

  Registry = ATL::CComCriticalSection::Init(this);
  if ( Registry >= 0 )
  {
    v3 = ATL::CRegKey::Open(
           (CHMESharedLibraryMonitor *)((char *)this + 136),
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\MediaPlayer\\Preferences\\HME\\",
           0x20219u);
    Registry = v3;
    if ( v3 )
    {
      if ( v3 > 0 )
        return (unsigned __int16)v3 | 0x80070000;
    }
    else
    {
      EventW = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)this + 20) = EventW;
      if ( EventW )
      {
        Registry = CHMESharedLibraryMonitor::_MonitorRegistry(this);
        if ( Registry >= 0 )
        {
          Registry = CHMESharedLibraryMonitor::_ReadRegistry(this, 0, v5);
          if ( Registry >= 0 )
            *((_QWORD *)this + 21) = CreateThread(
                                       0,
                                       0,
                                       (LPTHREAD_START_ROUTINE)CHMESharedLibraryMonitor::_RegistryWatchProc,
                                       this,
                                       0,
                                       0);
        }
      }
      else
      {
        return (unsigned int)-2147418113;
      }
    }
  }
  return (unsigned int)Registry;
}

```

## disassembly

```asm
0x14008af50  mov     [rsp+arg_0], rbx
0x14008af55  push    rdi
0x14008af56  sub     rsp, 30h
0x14008af5a  mov     rdi, rcx
0x14008af5d  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x14008af62  mov     ebx, eax
0x14008af64  test    eax, eax
0x14008af66  js      loc_14008B00C
0x14008af6c  lea     rcx, [rdi+88h]; this
0x14008af73  mov     r9d, 20219h; unsigned int
0x14008af79  lea     r8, aSoftwareMicros_9; "Software\\Microsoft\\MediaPlayer\\Prefe"...
0x14008af80  mov     rdx, 0FFFFFFFF80000002h; hKey
0x14008af87  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14008af8c  mov     ebx, eax
0x14008af8e  test    eax, eax
0x14008af90  jnz     short loc_14008B001
0x14008af92  xor     r9d, r9d; lpName
0x14008af95  xor     r8d, r8d; bInitialState
0x14008af98  xor     edx, edx; bManualReset
0x14008af9a  xor     ecx, ecx; lpEventAttributes
0x14008af9c  call    cs:__imp_CreateEventW
0x14008afa2  mov     [rdi+0A0h], rax
0x14008afa9  test    rax, rax
0x14008afac  jz      short loc_14008AFFA
0x14008afae  mov     rcx, rdi; this
0x14008afb1  call    ?_MonitorRegistry@CHMESharedLibraryMonitor@@IEAAJXZ; CHMESharedLibraryMonitor::_MonitorRegistry(void)
0x14008afb6  mov     ebx, eax
0x14008afb8  test    eax, eax
0x14008afba  js      short loc_14008B00C
0x14008afbc  xor     edx, edx; int
0x14008afbe  mov     rcx, rdi; this
0x14008afc1  call    ?_ReadRegistry@CHMESharedLibraryMonitor@@IEAAJH@Z; CHMESharedLibraryMonitor::_ReadRegistry(int)
0x14008afc6  mov     ebx, eax
0x14008afc8  test    eax, eax
0x14008afca  js      short loc_14008B00C
0x14008afcc  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x14008afd5  lea     r8, ?_RegistryWatchProc@CHMESharedLibraryMonitor@@KAKPEAX@Z; lpStartAddress
0x14008afdc  mov     r9, rdi; lpParameter
0x14008afdf  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x14008afe7  xor     edx, edx; dwStackSize
0x14008afe9  xor     ecx, ecx; lpThreadAttributes
0x14008afeb  call    cs:__imp_CreateThread
0x14008aff1  mov     [rdi+0A8h], rax
0x14008aff8  jmp     short loc_14008B00C
0x14008affa  mov     ebx, 8000FFFFh
0x14008afff  jmp     short loc_14008B00C
0x14008b001  jle     short loc_14008B00C
0x14008b003  movzx   ebx, ax
0x14008b006  or      ebx, 80070000h
0x14008b00c  mov     eax, ebx
0x14008b00e  mov     rbx, [rsp+38h+arg_0]
0x14008b013  add     rsp, 30h
0x14008b017  pop     rdi
0x14008b018  retn
```
