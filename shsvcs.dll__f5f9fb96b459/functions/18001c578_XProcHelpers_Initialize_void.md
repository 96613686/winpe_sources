# XProcHelpers::Initialize(void)

- ea: `0x18001c578`
- end: `0x18001c639`
- name: `?Initialize@XProcHelpers@@YAJXZ`
- size: `193`
- prototype: `__int64 __fastcall(XProcHelpers *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180023f30`

## callees

- `0x18001b404`
- `0x18001c550`
- `0x18001c578`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c5aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c5aa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001c598`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001c5ef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001c598`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001c5ef`

## pseudocode

```c
__int64 __fastcall XProcHelpers::Initialize(XProcHelpers *this)
{
  signed int LastError; // eax
  signed int v2; // ebx
  XProcHelpers::CSlowServiceInit *v3; // rax
  XProcHelpers::CSlowServiceInit *v4; // rdi
  HANDLE EventW; // rax
  __int64 result; // rax

  XProcHelpers::g_fShuttingDown = 0;
  XProcHelpers::g_hevtShuttingDown = CreateEventW(0, 1, 0, 0);
  if ( XProcHelpers::g_hevtShuttingDown )
    goto LABEL_5;
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  if ( v2 >= 0 )
  {
LABEL_5:
    v3 = (XProcHelpers::CSlowServiceInit *)operator new(0x10u);
    v4 = v3;
    if ( v3 )
    {
      *(_DWORD *)v3 = 0;
      *((_QWORD *)v3 + 1) = 0;
      EventW = CreateEventW(0, 1, 0, 0);
      *((_QWORD *)v4 + 1) = EventW;
      if ( EventW )
      {
        v2 = 0;
LABEL_11:
        XProcHelpers::g_pslowserviceinit = v4;
        goto LABEL_12;
      }
      v2 = -2147467259;
      XProcHelpers::CSlowServiceInit::`scalar deleting destructor'(v4);
    }
    else
    {
      v2 = -2147024882;
    }
    v4 = 0;
    goto LABEL_11;
  }
LABEL_12:
  result = (unsigned int)v2;
  XProcHelpers::g_fInitialized = v2 >= 0;
  return result;
}

```

## disassembly

```asm
0x18001c578  mov     [rsp+arg_0], rbx
0x18001c57d  push    rdi
0x18001c57e  sub     rsp, 20h
0x18001c582  xor     r9d, r9d; lpName
0x18001c585  mov     cs:?g_fShuttingDown@XProcHelpers@@3HA, 0; int XProcHelpers::g_fShuttingDown
0x18001c58f  xor     r8d, r8d; bInitialState
0x18001c592  xor     ecx, ecx; lpEventAttributes
0x18001c594  lea     edx, [r9+1]; bManualReset
0x18001c598  call    cs:__imp_CreateEventW
0x18001c59e  mov     cs:?g_hevtShuttingDown@XProcHelpers@@3PEAXEA, rax; void * XProcHelpers::g_hevtShuttingDown
0x18001c5a5  test    rax, rax
0x18001c5a8  jnz     short loc_18001C5C3
0x18001c5aa  call    cs:__imp_GetLastError
0x18001c5b0  mov     ebx, eax
0x18001c5b2  test    eax, eax
0x18001c5b4  jle     short loc_18001C5BF
0x18001c5b6  movzx   ebx, ax
0x18001c5b9  or      ebx, 80070000h
0x18001c5bf  test    ebx, ebx
0x18001c5c1  js      short loc_18001C61F
0x18001c5c3  mov     ecx, 10h; Size
0x18001c5c8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c5cd  mov     rdi, rax
0x18001c5d0  test    rax, rax
0x18001c5d3  jz      short loc_18001C611
0x18001c5d5  xor     r9d, r9d; lpName
0x18001c5d8  mov     dword ptr [rax], 0
0x18001c5de  xor     r8d, r8d; bInitialState
0x18001c5e1  mov     qword ptr [rax+8], 0
0x18001c5e9  xor     ecx, ecx; lpEventAttributes
0x18001c5eb  lea     edx, [r9+1]; bManualReset
0x18001c5ef  call    cs:__imp_CreateEventW
0x18001c5f5  mov     [rdi+8], rax
0x18001c5f9  test    rax, rax
0x18001c5fc  jz      short loc_18001C602
0x18001c5fe  xor     ebx, ebx
0x18001c600  jmp     short loc_18001C618
0x18001c602  mov     rcx, rdi; this
0x18001c605  mov     ebx, 80004005h
0x18001c60a  call    ??_GCSlowServiceInit@XProcHelpers@@QEAAPEAXI@Z; XProcHelpers::CSlowServiceInit::`scalar deleting destructor'(uint)
0x18001c60f  jmp     short loc_18001C616
0x18001c611  mov     ebx, 8007000Eh
0x18001c616  xor     edi, edi
0x18001c618  mov     cs:?g_pslowserviceinit@XProcHelpers@@3PEAVCSlowServiceInit@1@EA, rdi; XProcHelpers::CSlowServiceInit * XProcHelpers::g_pslowserviceinit
0x18001c61f  mov     ecx, ebx
0x18001c621  mov     eax, ebx
0x18001c623  mov     rbx, [rsp+28h+arg_0]
0x18001c628  not     ecx
0x18001c62a  shr     ecx, 1Fh
0x18001c62d  mov     cs:?g_fInitialized@XProcHelpers@@3HA, ecx; int XProcHelpers::g_fInitialized
0x18001c633  add     rsp, 20h
0x18001c637  pop     rdi
0x18001c638  retn
```
