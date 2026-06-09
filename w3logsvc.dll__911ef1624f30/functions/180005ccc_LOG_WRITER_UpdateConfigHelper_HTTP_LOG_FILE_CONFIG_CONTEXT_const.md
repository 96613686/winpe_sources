# LOG_WRITER::UpdateConfigHelper(HTTP_LOG_FILE_CONFIG_CONTEXT const *)

- ea: `0x180005ccc`
- end: `0x180005efe`
- name: `?UpdateConfigHelper@LOG_WRITER@@AEAAJPEBVHTTP_LOG_FILE_CONFIG_CONTEXT@@@Z`
- size: `562`
- prototype: `__int64 __fastcall(LOG_WRITER *__hidden this, const struct HTTP_LOG_FILE_CONFIG_CONTEXT *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x1800057a0`
- `0x180005bd4`

## callees

- `0x180001008`
- `0x180001048`
- `0x180002008`
- `0x180004fe4`
- `0x180005ccc`
- `0x180005f04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e4d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005d39`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005d43`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005e73`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005e7d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005d39`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005d43`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005e73`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005e7d`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180005d2f`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180005e69`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180005d2f`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180005e69`
- `iisutil!?Copy@MULTISZ@@QEAAHAEBV1@@Z` at `0x180005e3f`
- `iisutil!?Copy@MULTISZ@@QEAAHAEBV1@@Z` at `0x180005e3f`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180005e11`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180005e25`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180005e11`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180005e25`

## pseudocode

```c
__int64 __fastcall LOG_WRITER::UpdateConfigHelper(LOG_WRITER *this, const struct HTTP_LOG_FILE_CONFIG_CONTEXT *a2)
{
  int v4; // ebp
  BOOL v5; // r12d
  __int64 v6; // rax
  __int64 v7; // rbx
  signed int updated; // ebx
  HTTP_LOG_FILE_CONFIG_CONTEXT *v9; // rax
  HTTP_LOG_FILE_CONFIG_CONTEXT *v10; // rdi
  signed int LastError; // eax
  void *v13; // [rsp+50h] [rbp+8h] BYREF
  HTTP_LOG_FILE_CONFIG_CONTEXT *v14; // [rsp+58h] [rbp+10h]

  v13 = 0;
  v4 = 1;
  v5 = 0;
  if ( (*((_DWORD *)a2 + 57) & 0x4000) != 0 && (*((_BYTE *)a2 + 40) & 1) != 0 )
  {
    v6 = *((_QWORD *)this + 1);
    if ( !v6 || (*(_BYTE *)(v6 + 40) & 1) == 0 )
      v5 = 1;
  }
  v7 = *((_QWORD *)this + 1);
  if ( v7 )
  {
    MULTISZ::~MULTISZ((MULTISZ *)(v7 + 160));
    STRU::~STRU((STRU *)(v7 + 104));
    STRU::~STRU((STRU *)(v7 + 48));
    operator delete((void *)v7);
    *((_QWORD *)this + 1) = 0;
  }
  updated = 0;
  v9 = (HTTP_LOG_FILE_CONFIG_CONTEXT *)operator new(0xE8u);
  v14 = v9;
  if ( v9 )
    v10 = HTTP_LOG_FILE_CONFIG_CONTEXT::HTTP_LOG_FILE_CONFIG_CONTEXT(v9);
  else
    v10 = 0;
  if ( !v10 )
  {
LABEL_19:
    if ( updated < 0 )
      return (unsigned int)updated;
    goto LABEL_20;
  }
  *(_DWORD *)v10 = *(_DWORD *)a2;
  *((_DWORD *)v10 + 1) = *((_DWORD *)a2 + 1);
  *((_DWORD *)v10 + 2) = *((_DWORD *)a2 + 2);
  *((_DWORD *)v10 + 3) = *((_DWORD *)a2 + 3);
  *((_DWORD *)v10 + 57) ^= (*((_DWORD *)a2 + 57) ^ *((_DWORD *)v10 + 57)) & 0x4000;
  *((_DWORD *)v10 + 4) = *((_DWORD *)a2 + 4);
  *((_DWORD *)v10 + 5) = *((_DWORD *)a2 + 5);
  *((_DWORD *)v10 + 6) = *((_DWORD *)a2 + 6);
  *((_DWORD *)v10 + 7) = *((_DWORD *)a2 + 7);
  *((_DWORD *)v10 + 8) = *((_DWORD *)a2 + 8);
  *((_DWORD *)v10 + 9) = *((_DWORD *)a2 + 9);
  *((_DWORD *)v10 + 10) = *((_DWORD *)a2 + 10);
  *((_DWORD *)v10 + 54) = *((_DWORD *)a2 + 54);
  *((_DWORD *)v10 + 55) = *((_DWORD *)a2 + 55);
  updated = STRU::Copy(
              (HTTP_LOG_FILE_CONFIG_CONTEXT *)((char *)v10 + 48),
              (const struct HTTP_LOG_FILE_CONFIG_CONTEXT *)((char *)a2 + 48));
  if ( updated < 0
    || (updated = STRU::Copy(
                    (HTTP_LOG_FILE_CONFIG_CONTEXT *)((char *)v10 + 104),
                    (const struct HTTP_LOG_FILE_CONFIG_CONTEXT *)((char *)a2 + 104)),
        updated < 0) )
  {
LABEL_18:
    MULTISZ::~MULTISZ((HTTP_LOG_FILE_CONFIG_CONTEXT *)((char *)v10 + 160));
    STRU::~STRU((HTTP_LOG_FILE_CONFIG_CONTEXT *)((char *)v10 + 104));
    STRU::~STRU((HTTP_LOG_FILE_CONFIG_CONTEXT *)((char *)v10 + 48));
    operator delete(v10);
    goto LABEL_19;
  }
  if ( !MULTISZ::Copy(
          (HTTP_LOG_FILE_CONFIG_CONTEXT *)((char *)v10 + 160),
          (const struct HTTP_LOG_FILE_CONFIG_CONTEXT *)((char *)a2 + 160)) )
  {
    LastError = GetLastError();
    updated = LastError;
    if ( LastError > 0 )
      updated = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_18;
  }
  *((_QWORD *)this + 1) = v10;
LABEL_20:
  if ( (*(_BYTE *)(*((_QWORD *)this + 1) + 40LL) & 1) != 0 )
  {
    updated = LOG_WRITER::UpdateHeaders(this);
    if ( updated >= 0 )
    {
      if ( (*((_DWORD *)a2 + 57) & 0x410) == 0 && !v5 )
        v4 = 0;
      updated = LOG_WRITER::GetLogFileHandle(this, &v13, 0, v4);
      if ( updated < 0 && *((_DWORD *)this + 169) )
        return 0;
    }
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180005ccc  mov     [rsp+arg_10], rbx
0x180005cd1  mov     [rsp+arg_18], rbp
0x180005cd6  push    rsi
0x180005cd7  push    rdi
0x180005cd8  push    r12
0x180005cda  push    r14
0x180005cdc  push    r15
0x180005cde  sub     rsp, 20h
0x180005ce2  mov     r15, rdx
0x180005ce5  mov     rsi, rcx
0x180005ce8  mov     [rsp+48h+arg_0], 0
0x180005cf1  mov     ebp, 1
0x180005cf6  test    dword ptr [rdx+0E4h], 4000h
0x180005d00  jnz     short loc_180005D07
0x180005d02  xor     r12d, r12d
0x180005d05  jmp     short loc_180005D1F
0x180005d07  test    [rdx+28h], bpl
0x180005d0b  jz      short loc_180005D02
0x180005d0d  mov     rax, [rcx+8]
0x180005d11  test    rax, rax
0x180005d14  jz      short loc_180005D1C
0x180005d16  test    [rax+28h], bpl
0x180005d1a  jnz     short loc_180005D02
0x180005d1c  mov     r12d, ebp
0x180005d1f  mov     rbx, [rcx+8]
0x180005d23  test    rbx, rbx
0x180005d26  jz      short loc_180005D59
0x180005d28  lea     rcx, [rbx+0A0h]
0x180005d2f  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x180005d35  lea     rcx, [rbx+68h]
0x180005d39  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180005d3f  lea     rcx, [rbx+30h]
0x180005d43  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180005d49  mov     rcx, rbx; Block
0x180005d4c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005d51  mov     qword ptr [rsi+8], 0
0x180005d59  xor     ebx, ebx
0x180005d5b  mov     ecx, 0E8h; Size
0x180005d60  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005d65  mov     [rsp+48h+arg_8], rax
0x180005d6a  test    rax, rax
0x180005d6d  jz      short loc_180005D7C
0x180005d6f  mov     rcx, rax; this
0x180005d72  call    ??0HTTP_LOG_FILE_CONFIG_CONTEXT@@QEAA@XZ; HTTP_LOG_FILE_CONFIG_CONTEXT::HTTP_LOG_FILE_CONFIG_CONTEXT(void)
0x180005d77  mov     rdi, rax
0x180005d7a  jmp     short loc_180005D7E
0x180005d7c  xor     edi, edi
0x180005d7e  test    rdi, rdi
0x180005d81  jz      loc_180005E8B
0x180005d87  mov     eax, [r15]
0x180005d8a  mov     [rdi], eax
0x180005d8c  mov     eax, [r15+4]
0x180005d90  mov     [rdi+4], eax
0x180005d93  mov     eax, [r15+8]
0x180005d97  mov     [rdi+8], eax
0x180005d9a  mov     eax, [r15+0Ch]
0x180005d9e  mov     [rdi+0Ch], eax
0x180005da1  mov     eax, [rdi+0E4h]
0x180005da7  mov     ecx, eax
0x180005da9  xor     ecx, [r15+0E4h]
0x180005db0  and     ecx, 4000h
0x180005db6  xor     ecx, eax
0x180005db8  mov     [rdi+0E4h], ecx
0x180005dbe  mov     eax, [r15+10h]
0x180005dc2  mov     [rdi+10h], eax
0x180005dc5  mov     eax, [r15+14h]
0x180005dc9  mov     [rdi+14h], eax
0x180005dcc  mov     eax, [r15+18h]
0x180005dd0  mov     [rdi+18h], eax
0x180005dd3  mov     eax, [r15+1Ch]
0x180005dd7  mov     [rdi+1Ch], eax
0x180005dda  mov     eax, [r15+20h]
0x180005dde  mov     [rdi+20h], eax
0x180005de1  mov     eax, [r15+24h]
0x180005de5  mov     [rdi+24h], eax
0x180005de8  mov     eax, [r15+28h]
0x180005dec  mov     [rdi+28h], eax
0x180005def  mov     eax, [r15+0D8h]
0x180005df6  mov     [rdi+0D8h], eax
0x180005dfc  mov     eax, [r15+0DCh]
0x180005e03  mov     [rdi+0DCh], eax
0x180005e09  lea     rdx, [r15+30h]
0x180005e0d  lea     rcx, [rdi+30h]
0x180005e11  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x180005e17  mov     ebx, eax
0x180005e19  test    eax, eax
0x180005e1b  js      short loc_180005E62
0x180005e1d  lea     rdx, [r15+68h]
0x180005e21  lea     rcx, [rdi+68h]
0x180005e25  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x180005e2b  mov     ebx, eax
0x180005e2d  test    eax, eax
0x180005e2f  js      short loc_180005E62
0x180005e31  lea     rdx, [r15+0A0h]
0x180005e38  lea     rcx, [rdi+0A0h]
0x180005e3f  call    cs:__imp_?Copy@MULTISZ@@QEAAHAEBV1@@Z; MULTISZ::Copy(MULTISZ const &)
0x180005e45  test    eax, eax
0x180005e47  jnz     loc_180005EF8
0x180005e4d  call    cs:__imp_GetLastError
0x180005e53  mov     ebx, eax
0x180005e55  test    eax, eax
0x180005e57  jle     short loc_180005E62
0x180005e59  movzx   ebx, ax
0x180005e5c  or      ebx, 80070000h
0x180005e62  lea     rcx, [rdi+0A0h]
0x180005e69  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x180005e6f  lea     rcx, [rdi+68h]
0x180005e73  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180005e79  lea     rcx, [rdi+30h]
0x180005e7d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180005e83  mov     rcx, rdi; Block
0x180005e86  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005e8b  test    ebx, ebx
0x180005e8d  js      short loc_180005EDF
0x180005e8f  mov     rax, [rsi+8]
0x180005e93  test    [rax+28h], bpl
0x180005e97  jz      short loc_180005EDF
0x180005e99  mov     rcx, rsi; this
0x180005e9c  call    ?UpdateHeaders@LOG_WRITER@@AEAAJXZ; LOG_WRITER::UpdateHeaders(void)
0x180005ea1  mov     ebx, eax
0x180005ea3  test    eax, eax
0x180005ea5  js      short loc_180005EDF
0x180005ea7  test    dword ptr [r15+0E4h], 410h
0x180005eb2  jnz     short loc_180005EBB
0x180005eb4  test    r12d, r12d
0x180005eb7  jnz     short loc_180005EBB
0x180005eb9  xor     ebp, ebp
0x180005ebb  mov     r9d, ebp; int
0x180005ebe  xor     r8d, r8d; unsigned int
0x180005ec1  lea     rdx, [rsp+48h+arg_0]; void **
0x180005ec6  mov     rcx, rsi; this
0x180005ec9  call    ?GetLogFileHandle@LOG_WRITER@@AEAAJPEAPEAXKH@Z; LOG_WRITER::GetLogFileHandle(void * *,ulong,int)
0x180005ece  mov     ebx, eax
0x180005ed0  test    eax, eax
0x180005ed2  jns     short loc_180005EDF
0x180005ed4  xor     eax, eax
0x180005ed6  cmp     [rsi+2A4h], eax
0x180005edc  cmovnz  ebx, eax
0x180005edf  mov     eax, ebx
0x180005ee1  mov     rbx, [rsp+48h+arg_10]
0x180005ee6  mov     rbp, [rsp+48h+arg_18]
0x180005eeb  add     rsp, 20h
0x180005eef  pop     r15
0x180005ef1  pop     r14
0x180005ef3  pop     r12
0x180005ef5  pop     rdi
0x180005ef6  pop     rsi
0x180005ef7  retn
0x180005ef8  mov     [rsi+8], rdi
0x180005efc  jmp     short loc_180005E8F
```
