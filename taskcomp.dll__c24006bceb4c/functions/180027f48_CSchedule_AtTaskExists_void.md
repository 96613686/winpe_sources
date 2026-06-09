# CSchedule::_AtTaskExists(void)

- ea: `0x180027f48`
- end: `0x180028038`
- name: `?_AtTaskExists@CSchedule@@AEAAJXZ`
- size: `240`
- prototype: `__int64 __fastcall(CSchedule *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180027228`

## callees

- `0x180010b94`
- `0x180027f48`
- `0x1800299d8`
- `0x180029a70`
- `0x18002e572`
- `0x18002e5b0`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180027f8a`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180027f8a`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180027fe7`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180027fe7`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180027ffc`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180027ffc`

## pseudocode

```c
__int64 __fastcall CSchedule::_AtTaskExists(CSchedule *this)
{
  HANDLE FirstFileW; // rsi
  struct CJob *v3; // rdi
  unsigned int v4; // ebx
  int v5; // eax
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+20h] [rbp-268h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(&g_wszAtJobSearchPath, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
    return 1;
  v3 = CJob::Create();
  if ( !v3 )
    return 2147942414LL;
  v4 = 1;
  while ( 1 )
  {
    if ( !(unsigned int)IsValidAtFilename(FindFileData.cFileName) )
      goto LABEL_9;
    v5 = LoadAtJob(v3, FindFileData.cFileName);
    if ( v5 < 0 )
      break;
    if ( (*((_DWORD *)v3 + 22) & 0x200000) != 0 )
    {
      v4 = 0;
      goto LABEL_13;
    }
LABEL_9:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
      goto LABEL_13;
  }
  v4 = v5;
LABEL_13:
  FindClose(FirstFileW);
  (*(void (__fastcall **)(struct CJob *))(*(_QWORD *)v3 + 16LL))(v3);
  return v4;
}

```

## disassembly

```asm
0x180027f48  mov     [rsp+arg_0], rbx
0x180027f4d  mov     [rsp+arg_8], rsi
0x180027f52  push    rdi
0x180027f53  sub     rsp, 280h
0x180027f5a  mov     rax, cs:__security_cookie
0x180027f61  xor     rax, rsp
0x180027f64  mov     [rsp+288h+var_18], rax
0x180027f6c  xor     edx, edx; Val
0x180027f6e  lea     rcx, [rsp+288h+FindFileData]; void *
0x180027f73  mov     r8d, 250h; Size
0x180027f79  call    memset_0
0x180027f7e  lea     rdx, [rsp+288h+FindFileData]; lpFindFileData
0x180027f83  lea     rcx, ?g_wszAtJobSearchPath@@3PAGA; lpFileName
0x180027f8a  call    cs:__imp_FindFirstFileW
0x180027f90  mov     rsi, rax
0x180027f93  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180027f97  jnz     short loc_180027F9E
0x180027f99  lea     eax, [rsi+2]
0x180027f9c  jmp     short loc_180028013
0x180027f9e  call    ?Create@CJob@@SAPEAV1@XZ; CJob::Create(void)
0x180027fa3  mov     rdi, rax
0x180027fa6  test    rax, rax
0x180027fa9  jnz     short loc_180027FB2
0x180027fab  mov     eax, 8007000Eh
0x180027fb0  jmp     short loc_180028013
0x180027fb2  mov     ebx, 1
0x180027fb7  lea     rcx, [rsp+288h+FindFileData.cFileName]; unsigned __int16 *
0x180027fbc  call    ?IsValidAtFilename@@YAHPEBG@Z; IsValidAtFilename(ushort const *)
0x180027fc1  test    eax, eax
0x180027fc3  jz      short loc_180027FDF
0x180027fc5  lea     rdx, [rsp+288h+FindFileData.cFileName]; unsigned __int16 *
0x180027fca  mov     rcx, rdi; this
0x180027fcd  call    ?LoadAtJob@@YAJPEAVCJob@@PEAG@Z; LoadAtJob(CJob *,ushort *)
0x180027fd2  test    eax, eax
0x180027fd4  js      short loc_180027FF7
0x180027fd6  test    dword ptr [rdi+58h], 200000h
0x180027fdd  jnz     short loc_180027FF3
0x180027fdf  lea     rdx, [rsp+288h+FindFileData]; lpFindFileData
0x180027fe4  mov     rcx, rsi; hFindFile
0x180027fe7  call    cs:__imp_FindNextFileW
0x180027fed  test    eax, eax
0x180027fef  jnz     short loc_180027FB7
0x180027ff1  jmp     short loc_180027FF9
0x180027ff3  xor     ebx, ebx
0x180027ff5  jmp     short loc_180027FF9
0x180027ff7  mov     ebx, eax
0x180027ff9  mov     rcx, rsi; hFindFile
0x180027ffc  call    cs:__imp_FindClose
0x180028002  mov     rcx, [rdi]
0x180028005  mov     rax, [rcx+10h]
0x180028009  mov     rcx, rdi
0x18002800c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028011  mov     eax, ebx
0x180028013  mov     rcx, [rsp+288h+var_18]
0x18002801b  xor     rcx, rsp; StackCookie
0x18002801e  call    __security_check_cookie
0x180028023  lea     r11, [rsp+288h+var_8]
0x18002802b  mov     rbx, [r11+10h]
0x18002802f  mov     rsi, [r11+18h]
0x180028033  mov     rsp, r11
0x180028036  pop     rdi
0x180028037  retn
```
