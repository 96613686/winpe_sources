# LOG_WRITER::Initialize(HTTP_LOG_FILE_CONFIG_CONTEXT const *)

- ea: `0x1800057a0`
- end: `0x180005879`
- name: `?Initialize@LOG_WRITER@@QEAAJPEBVHTTP_LOG_FILE_CONFIG_CONTEXT@@@Z`
- size: `217`
- prototype: `__int64 __fastcall(LOG_WRITER *__hidden this, const struct HTTP_LOG_FILE_CONFIG_CONTEXT *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180007670`
- `0x180008174`

## callees

- `0x1800057a0`
- `0x180005ccc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800057d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800057d5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800057cb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800057cb`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800057f7`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800057f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000585f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000585f`
- `iisutil!?Resize@STRA@@QEAAJK@Z` at `0x18000581f`
- `iisutil!?Resize@STRA@@QEAAJK@Z` at `0x18000581f`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180005839`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180005839`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180005853`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180005853`

## pseudocode

```c
__int64 __fastcall LOG_WRITER::Initialize(LOG_WRITER *this, const struct HTTP_LOG_FILE_CONFIG_CONTEXT *a2)
{
  int updated; // ebx
  signed int LastError; // eax

  if ( a2 )
  {
    if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)this + 17, 0x1000u) )
    {
      InitializeSRWLock((PSRWLOCK)this + 90);
      updated = LOG_WRITER::UpdateConfigHelper(this, a2);
      if ( updated >= 0 )
      {
        updated = STRA::Resize((LOG_WRITER *)((char *)this + 128), *((_DWORD *)g_pLogSvcAdmin + 3));
        if ( updated >= 0 )
        {
          updated = STRA::Copy((LOG_WRITER *)((char *)this + 496), "-");
          if ( updated >= 0 )
          {
            updated = STRU::Copy((LOG_WRITER *)((char *)this + 560), L"-");
            if ( updated >= 0 )
              *((_QWORD *)this + 83) = GetTickCount64();
          }
        }
      }
    }
    else
    {
      LastError = GetLastError();
      updated = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1800057a0  mov     [rsp+arg_0], rbx
0x1800057a5  push    rdi
0x1800057a6  sub     rsp, 20h
0x1800057aa  mov     rbx, rdx
0x1800057ad  mov     rdi, rcx
0x1800057b0  test    rdx, rdx
0x1800057b3  jnz     short loc_1800057BF
0x1800057b5  mov     ebx, 80070057h
0x1800057ba  jmp     loc_18000586C
0x1800057bf  add     rcx, 2A8h; lpCriticalSection
0x1800057c6  mov     edx, 1000h; dwSpinCount
0x1800057cb  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800057d1  test    eax, eax
0x1800057d3  jnz     short loc_1800057F0
0x1800057d5  call    cs:__imp_GetLastError
0x1800057db  mov     ebx, eax
0x1800057dd  test    eax, eax
0x1800057df  jle     loc_18000586C
0x1800057e5  movzx   ebx, ax
0x1800057e8  or      ebx, 80070000h
0x1800057ee  jmp     short loc_18000586C
0x1800057f0  lea     rcx, [rdi+2D0h]; SRWLock
0x1800057f7  call    cs:__imp_InitializeSRWLock
0x1800057fd  mov     rdx, rbx; struct HTTP_LOG_FILE_CONFIG_CONTEXT *
0x180005800  mov     rcx, rdi; this
0x180005803  call    ?UpdateConfigHelper@LOG_WRITER@@AEAAJPEBVHTTP_LOG_FILE_CONFIG_CONTEXT@@@Z; LOG_WRITER::UpdateConfigHelper(HTTP_LOG_FILE_CONFIG_CONTEXT const *)
0x180005808  mov     ebx, eax
0x18000580a  test    eax, eax
0x18000580c  js      short loc_18000586C
0x18000580e  mov     rdx, cs:?g_pLogSvcAdmin@@3PEAVLOG_SVC_ADMIN@@EA; LOG_SVC_ADMIN * g_pLogSvcAdmin
0x180005815  lea     rcx, [rdi+80h]
0x18000581c  mov     edx, [rdx+0Ch]
0x18000581f  call    cs:__imp_?Resize@STRA@@QEAAJK@Z; STRA::Resize(ulong)
0x180005825  mov     ebx, eax
0x180005827  test    eax, eax
0x180005829  js      short loc_18000586C
0x18000582b  lea     rcx, [rdi+1F0h]
0x180005832  lea     rdx, asc_180012088; "-"
0x180005839  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x18000583f  mov     ebx, eax
0x180005841  test    eax, eax
0x180005843  js      short loc_18000586C
0x180005845  lea     rcx, [rdi+230h]
0x18000584c  lea     rdx, asc_18001208C; "-"
0x180005853  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180005859  mov     ebx, eax
0x18000585b  test    eax, eax
0x18000585d  js      short loc_18000586C
0x18000585f  call    cs:__imp_GetTickCount64
0x180005865  mov     [rdi+298h], rax
0x18000586c  mov     eax, ebx
0x18000586e  mov     rbx, [rsp+28h+arg_0]
0x180005873  add     rsp, 20h
0x180005877  pop     rdi
0x180005878  retn
```
