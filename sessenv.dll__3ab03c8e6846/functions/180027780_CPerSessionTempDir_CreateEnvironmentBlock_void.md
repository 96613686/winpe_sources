# CPerSessionTempDir::CreateEnvironmentBlock(void)

- ea: `0x180027780`
- end: `0x18002783e`
- name: `?CreateEnvironmentBlock@CPerSessionTempDir@@AEAAJXZ`
- size: `190`
- prototype: `__int64 __fastcall(CPerSessionTempDir *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180027cdc`

## callees

- `0x180003f30`
- `0x1800130a8`
- `0x180027780`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800277d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800277d0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800277c6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800277c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800277af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800277af`
- `profapi!__imp_CreateEnvBlock` at `0x180027800`
- `profapi!__imp_CreateEnvBlock` at `0x180027800`
- `profapi!__imp_DestroyEnvBlock` at `0x1800277a2`
- `profapi!__imp_DestroyEnvBlock` at `0x1800277a2`

## string_xrefs

- `0x1800277ec`: `OpenThreadToken failed: 0x%x in %s`
- `0x180027816`: `CPerSessionTempDir::CreateEnvironmentBlock`
- `0x18002780f`: `::CreateEnvironmentBlock failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CPerSessionTempDir::CreateEnvironmentBlock(CPerSessionTempDir *this)
{
  _QWORD *v1; // rdi
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  unsigned int v4; // ebx
  int EnvBlock; // eax
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  v1 = (_QWORD *)((char *)this + 1608);
  TokenHandle = 0;
  if ( *((_QWORD *)this + 201) )
  {
    DestroyEnvBlock();
    *v1 = 0;
  }
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_8;
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( (v4 & 0x80000000) == 0 )
  {
LABEL_8:
    EnvBlock = CreateEnvBlock(v1, TokenHandle, 0);
    v4 = EnvBlock;
    if ( EnvBlock < 0 )
      _DbgPrintMessage(
        8,
        "::CreateEnvironmentBlock failed: 0x%x in %s",
        (unsigned int)EnvBlock,
        "CPerSessionTempDir::CreateEnvironmentBlock");
  }
  else
  {
    _DbgPrintMessage(8, "OpenThreadToken failed: 0x%x in %s", v4, "CPerSessionTempDir::CreateEnvironmentBlock");
  }
  SmartHANDLE::~SmartHANDLE((SmartHANDLE *)&TokenHandle);
  return v4;
}

```

## disassembly

```asm
0x180027780  mov     [rsp+arg_8], rbx
0x180027785  push    rdi
0x180027786  sub     rsp, 20h
0x18002778a  lea     rdi, [rcx+648h]
0x180027791  mov     [rsp+28h+TokenHandle], 0
0x18002779a  mov     rcx, [rdi]
0x18002779d  test    rcx, rcx
0x1800277a0  jz      short loc_1800277AF
0x1800277a2  call    cs:__imp_DestroyEnvBlock
0x1800277a8  mov     qword ptr [rdi], 0
0x1800277af  call    cs:__imp_GetCurrentThread
0x1800277b5  mov     edx, 8; DesiredAccess
0x1800277ba  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1800277bf  mov     rcx, rax; ThreadHandle
0x1800277c2  lea     r8d, [rdx-7]; OpenAsSelf
0x1800277c6  call    cs:__imp_OpenThreadToken
0x1800277cc  test    eax, eax
0x1800277ce  jnz     short loc_1800277F5
0x1800277d0  call    cs:__imp_GetLastError
0x1800277d6  mov     ebx, eax
0x1800277d8  test    eax, eax
0x1800277da  jle     short loc_1800277E5
0x1800277dc  movzx   ebx, ax
0x1800277df  or      ebx, 80070000h
0x1800277e5  test    ebx, ebx
0x1800277e7  jns     short loc_1800277F5
0x1800277e9  mov     r8d, ebx
0x1800277ec  lea     rdx, aOpenthreadtoke; "OpenThreadToken failed: 0x%x in %s"
0x1800277f3  jmp     short loc_180027816
0x1800277f5  mov     rdx, [rsp+28h+TokenHandle]
0x1800277fa  xor     r8d, r8d
0x1800277fd  mov     rcx, rdi
0x180027800  call    cs:__imp_CreateEnvBlock
0x180027806  mov     ebx, eax
0x180027808  test    eax, eax
0x18002780a  jns     short loc_180027827
0x18002780c  mov     r8d, eax
0x18002780f  lea     rdx, aCreateenvironm_0; "::CreateEnvironmentBlock failed: 0x%x i"...
0x180027816  lea     r9, aCpersessiontem_7; "CPerSessionTempDir::CreateEnvironmentBl"...
0x18002781d  mov     ecx, 8; int
0x180027822  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180027827  lea     rcx, [rsp+28h+TokenHandle]; this
0x18002782c  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x180027831  mov     eax, ebx
0x180027833  mov     rbx, [rsp+28h+arg_8]
0x180027838  add     rsp, 20h
0x18002783c  pop     rdi
0x18002783d  retn
```
