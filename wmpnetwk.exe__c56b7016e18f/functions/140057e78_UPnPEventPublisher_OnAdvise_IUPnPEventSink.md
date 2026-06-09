# UPnPEventPublisher::OnAdvise(IUPnPEventSink *)

- ea: `0x140057e78`
- end: `0x140057f75`
- name: `?OnAdvise@UPnPEventPublisher@@QEAAJPEAUIUPnPEventSink@@@Z`
- size: `253`
- prototype: `int(UPnPEventPublisher *__hidden this, struct IUPnPEventSink *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140059420`
- `0x14005c27c`
- `0x140060434`

## callees

- `0x140057e78`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x140057eac`
- `KERNEL32!EnterCriticalSection` at `0x140057eac`
- `KERNEL32!LeaveCriticalSection` at `0x140057f62`
- `KERNEL32!LeaveCriticalSection` at `0x140057f62`
- `KERNEL32!CreateTimerQueue` at `0x140057f1d`
- `KERNEL32!CreateTimerQueue` at `0x140057f1d`
- `KERNEL32!GetLastError` at `0x140057f2c`
- `KERNEL32!GetLastError` at `0x140057f2c`
- `ole32!CreateStreamOnHGlobal` at `0x140057eda`
- `ole32!CreateStreamOnHGlobal` at `0x140057eda`
- `ole32!CoMarshalInterface` at `0x140057f0a`
- `ole32!CoMarshalInterface` at `0x140057f0a`

## pseudocode

```c
__int64 __fastcall UPnPEventPublisher::OnAdvise(UPnPEventPublisher *this, IUnknown *a2)
{
  int StreamOnHGlobal; // ebx
  HANDLE TimerQueue; // rax
  signed int LastError; // eax

  if ( *((_DWORD *)this + 2) == 1 )
    return 2147943515LL;
  if ( !a2 )
    return 2147942487LL;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( *((_DWORD *)this + 2) == 1 )
  {
    StreamOnHGlobal = -2147023781;
  }
  else if ( *((_QWORD *)this + 2) )
  {
    StreamOnHGlobal = -2147418113;
  }
  else
  {
    StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, (LPSTREAM *)this + 2);
    if ( StreamOnHGlobal >= 0 )
    {
      StreamOnHGlobal = CoMarshalInterface(*((LPSTREAM *)this + 2), &IID_IUPnPEventSink, a2, 3u, 0, 1u);
      if ( StreamOnHGlobal >= 0 )
      {
        if ( *((_QWORD *)this + 14) == -1 )
        {
          TimerQueue = CreateTimerQueue();
          *((_QWORD *)this + 14) = TimerQueue;
          if ( !TimerQueue )
          {
            LastError = GetLastError();
            StreamOnHGlobal = LastError;
            if ( LastError > 0 )
              StreamOnHGlobal = (unsigned __int16)LastError | 0x80070000;
            *((_QWORD *)this + 14) = -1;
          }
        }
        if ( StreamOnHGlobal >= 0 )
          *((_DWORD *)this + 36) = 1;
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  return (unsigned int)StreamOnHGlobal;
}

```

## disassembly

```asm
0x140057e78  push    rbx
0x140057e7a  push    rbp
0x140057e7b  push    rsi
0x140057e7c  push    rdi
0x140057e7d  push    r14
0x140057e7f  sub     rsp, 30h
0x140057e83  cmp     dword ptr [rcx+8], 1
0x140057e87  mov     rbp, rdx
0x140057e8a  mov     rdi, rcx
0x140057e8d  jnz     short loc_140057E99
0x140057e8f  mov     eax, 8007045Bh
0x140057e94  jmp     loc_140057F6A
0x140057e99  test    rbp, rbp
0x140057e9c  jnz     short loc_140057EA8
0x140057e9e  mov     eax, 80070057h
0x140057ea3  jmp     loc_140057F6A
0x140057ea8  add     rcx, 40h ; '@'; lpCriticalSection
0x140057eac  call    cs:__imp_EnterCriticalSection
0x140057eb2  cmp     dword ptr [rdi+8], 1
0x140057eb6  jnz     short loc_140057EC2
0x140057eb8  mov     ebx, 8007045Bh
0x140057ebd  jmp     loc_140057F5E
0x140057ec2  lea     rsi, [rdi+10h]
0x140057ec6  cmp     qword ptr [rsi], 0
0x140057eca  jnz     loc_140057F59
0x140057ed0  mov     r8, rsi; ppstm
0x140057ed3  mov     edx, 1; fDeleteOnRelease
0x140057ed8  xor     ecx, ecx; hGlobal
0x140057eda  call    cs:__imp_CreateStreamOnHGlobal
0x140057ee0  mov     ebx, eax
0x140057ee2  test    eax, eax
0x140057ee4  js      short loc_140057F5E
0x140057ee6  mov     rcx, [rsi]; pStm
0x140057ee9  lea     rdx, IID_IUPnPEventSink; riid
0x140057ef0  mov     [rsp+58h+mshlflags], 1; mshlflags
0x140057ef8  mov     r9d, 3; dwDestContext
0x140057efe  mov     r8, rbp; pUnk
0x140057f01  mov     [rsp+58h+pvDestContext], 0; pvDestContext
0x140057f0a  call    cs:__imp_CoMarshalInterface
0x140057f10  mov     ebx, eax
0x140057f12  test    eax, eax
0x140057f14  js      short loc_140057F5E
0x140057f16  cmp     qword ptr [rdi+70h], 0FFFFFFFFFFFFFFFFh
0x140057f1b  jnz     short loc_140057F49
0x140057f1d  call    cs:__imp_CreateTimerQueue
0x140057f23  mov     [rdi+70h], rax
0x140057f27  test    rax, rax
0x140057f2a  jnz     short loc_140057F49
0x140057f2c  call    cs:__imp_GetLastError
0x140057f32  mov     ebx, eax
0x140057f34  test    eax, eax
0x140057f36  jle     short loc_140057F41
0x140057f38  movzx   ebx, ax
0x140057f3b  or      ebx, 80070000h
0x140057f41  mov     qword ptr [rdi+70h], 0FFFFFFFFFFFFFFFFh
0x140057f49  test    ebx, ebx
0x140057f4b  js      short loc_140057F5E
0x140057f4d  mov     dword ptr [rdi+90h], 1
0x140057f57  jmp     short loc_140057F5E
0x140057f59  mov     ebx, 8000FFFFh
0x140057f5e  lea     rcx, [rdi+40h]; lpCriticalSection
0x140057f62  call    cs:__imp_LeaveCriticalSection
0x140057f68  mov     eax, ebx
0x140057f6a  add     rsp, 30h
0x140057f6e  pop     r14
0x140057f70  pop     rdi
0x140057f71  pop     rsi
0x140057f72  pop     rbp
0x140057f73  pop     rbx
0x140057f74  retn
```
