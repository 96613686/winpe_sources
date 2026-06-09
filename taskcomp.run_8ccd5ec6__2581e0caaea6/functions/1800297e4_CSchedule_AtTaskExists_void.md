# CSchedule::_AtTaskExists(void)

- ea: `0x1800297e4`
- end: `0x1800298ea`
- name: `?_AtTaskExists@CSchedule@@AEAAJXZ`
- size: `262`
- prototype: `__int64 __fastcall(CSchedule *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180028a3c`

## callees

- `0x1800115d0`
- `0x1800297e4`
- `0x18002b40c`
- `0x18002b4a4`
- `0x1800306c2`
- `0x180030700`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180029826`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180029826`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002988c`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002988c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800298a7`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800298a7`

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
0x1800297e4  mov     [rsp+arg_0], rbx
0x1800297e9  mov     [rsp+arg_8], rsi
0x1800297ee  push    rdi
0x1800297ef  sub     rsp, 280h
0x1800297f6  mov     rax, cs:__security_cookie
0x1800297fd  xor     rax, rsp
0x180029800  mov     [rsp+288h+var_18], rax
0x180029808  xor     edx, edx; Val
0x18002980a  lea     rcx, [rsp+288h+FindFileData]; void *
0x18002980f  mov     r8d, 250h; Size
0x180029815  call    memset_0
0x18002981a  lea     rdx, [rsp+288h+FindFileData]; lpFindFileData
0x18002981f  lea     rcx, ?g_wszAtJobSearchPath@@3PAGA; lpFileName
0x180029826  call    cs:__imp_FindFirstFileW
0x18002982d  nop     dword ptr [rax+rax+00h]
0x180029832  mov     rsi, rax
0x180029835  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180029839  jnz     short loc_180029843
0x18002983b  lea     eax, [rsi+2]
0x18002983e  jmp     loc_1800298C4
0x180029843  call    ?Create@CJob@@SAPEAV1@XZ; CJob::Create(void)
0x180029848  mov     rdi, rax
0x18002984b  test    rax, rax
0x18002984e  jnz     short loc_180029857
0x180029850  mov     eax, 8007000Eh
0x180029855  jmp     short loc_1800298C4
0x180029857  mov     ebx, 1
0x18002985c  lea     rcx, [rsp+288h+FindFileData.cFileName]; unsigned __int16 *
0x180029861  call    ?IsValidAtFilename@@YAHPEBG@Z; IsValidAtFilename(ushort const *)
0x180029866  test    eax, eax
0x180029868  jz      short loc_180029884
0x18002986a  lea     rdx, [rsp+288h+FindFileData.cFileName]; unsigned __int16 *
0x18002986f  mov     rcx, rdi; this
0x180029872  call    ?LoadAtJob@@YAJPEAVCJob@@PEAG@Z; LoadAtJob(CJob *,ushort *)
0x180029877  test    eax, eax
0x180029879  js      short loc_1800298A2
0x18002987b  test    dword ptr [rdi+58h], 200000h
0x180029882  jnz     short loc_18002989E
0x180029884  lea     rdx, [rsp+288h+FindFileData]; lpFindFileData
0x180029889  mov     rcx, rsi; hFindFile
0x18002988c  call    cs:__imp_FindNextFileW
0x180029893  nop     dword ptr [rax+rax+00h]
0x180029898  test    eax, eax
0x18002989a  jnz     short loc_18002985C
0x18002989c  jmp     short loc_1800298A4
0x18002989e  xor     ebx, ebx
0x1800298a0  jmp     short loc_1800298A4
0x1800298a2  mov     ebx, eax
0x1800298a4  mov     rcx, rsi; hFindFile
0x1800298a7  call    cs:__imp_FindClose
0x1800298ae  nop     dword ptr [rax+rax+00h]
0x1800298b3  mov     rcx, [rdi]
0x1800298b6  mov     rax, [rcx+10h]
0x1800298ba  mov     rcx, rdi
0x1800298bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800298c2  mov     eax, ebx
0x1800298c4  mov     rcx, [rsp+288h+var_18]
0x1800298cc  xor     rcx, rsp; StackCookie
0x1800298cf  call    __security_check_cookie
0x1800298d4  lea     r11, [rsp+288h+var_8]
0x1800298dc  mov     rbx, [r11+10h]
0x1800298e0  mov     rsi, [r11+18h]
0x1800298e4  mov     rsp, r11
0x1800298e7  pop     rdi
0x1800298e8  retn
```
