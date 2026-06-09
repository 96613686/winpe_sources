# StreamHelper::CreateFileAndPath(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *,int,void * *)

- ea: `0x180034128`
- end: `0x18003430a`
- name: `?CreateFileAndPath@StreamHelper@@SAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXHPEAPEAX@Z`
- size: `482`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, DWORD dwDesiredAccess@<edx>, DWORD dwShareMode@<r8d>, struct _SECURITY_ATTRIBUTES *@<r9>, DWORD, unsigned int, void *, int, void **)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180033ebc`
- `0x18004eb78`
- `0x18004f198`

## callees

- `0x180034128`
- `0x180034310`
- `0x1800396c8`
- `0x180039898`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800341a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034209`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800341a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034209`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003417d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800341f2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003417d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800341f2`

## pseudocode

```c
__int64 __fastcall StreamHelper::CreateFileAndPath(
        const unsigned __int16 *a1,
        DWORD dwDesiredAccess,
        DWORD dwShareMode,
        struct _SECURITY_ATTRIBUTES *a4,
        DWORD dwCreationDisposition,
        signed int AllFolders,
        void *a7,
        int a8,
        void **a9)
{
  HANDLE FileW; // rdi
  signed int LastError; // eax
  signed int v15; // eax
  unsigned int v16; // ecx
  void *v17; // rax
  void *v18; // rax

  AllFolders = 0;
  if ( (Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits & 0x20) != 0 )
  {
    v18 = _t_address();
    EtwTraceMessage(&ETWMESSAGE, v18, a1, -2, &dwCreationDisposition, 4, 0, -1);
  }
  FileW = CreateFileW(a1, dwDesiredAccess, dwShareMode, 0, dwCreationDisposition, 0, 0);
  if ( FileW != (HANDLE)-1LL )
    goto LABEL_4;
  LastError = GetLastError();
  if ( !a8 || LastError != 3 )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    AllFolders = LastError;
    if ( (Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits & 0x20) == 0 )
      goto LABEL_4;
    goto LABEL_19;
  }
  AllFolders = StreamHelper::CreateAllFolders(a1);
  if ( AllFolders < 0 )
  {
    if ( (Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits & 0x20) == 0 )
      goto LABEL_4;
    goto LABEL_19;
  }
  FileW = CreateFileW(a1, dwDesiredAccess, dwShareMode, 0, dwCreationDisposition, 0, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    AllFolders = 0;
    goto LABEL_4;
  }
  v15 = GetLastError();
  v16 = v15;
  if ( v15 > 0 )
    v16 = (unsigned __int16)v15 | 0x80070000;
  AllFolders = v16;
  if ( (int)(v16 + 0x80000000) >= 0
    && v16 != -2147024894
    && (Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits & 0x20) != 0 )
  {
LABEL_19:
    v17 = _t_address();
    EtwTraceMessage(&ETWMESSAGE, v17, a1, -2, &AllFolders, 4, 0, -1);
  }
LABEL_4:
  *a9 = FileW;
  return (unsigned int)AllFolders;
}

```

## disassembly

```asm
0x180034128  push    rbp
0x18003412a  push    rbx
0x18003412b  push    rsi
0x18003412c  push    rdi
0x18003412d  push    r13
0x18003412f  push    r14
0x180034131  mov     rbp, rsp
0x180034134  sub     rsp, 48h
0x180034138  or      r13, 0FFFFFFFFFFFFFFFFh
0x18003413c  mov     [rbp+arg_28], 0
0x180034143  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits, 20h
0x18003414a  mov     esi, r8d
0x18003414d  mov     r14d, edx
0x180034150  mov     rbx, rcx
0x180034153  jnz     loc_1800342B0
0x180034159  mov     eax, [rbp+arg_20]
0x18003415c  xor     r9d, r9d; lpSecurityAttributes
0x18003415f  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180034168  mov     r8d, esi; dwShareMode
0x18003416b  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180034173  mov     edx, r14d; dwDesiredAccess
0x180034176  mov     rcx, rbx; lpFileName
0x180034179  mov     [rsp+48h+dwCreationDisposition], eax; dwCreationDisposition
0x18003417d  call    cs:__imp_CreateFileW
0x180034183  mov     rdi, rax
0x180034186  cmp     rax, r13
0x180034189  jz      short loc_1800341A2
0x18003418b  mov     rax, [rbp+arg_40]
0x18003418f  mov     [rax], rdi
0x180034192  mov     eax, [rbp+arg_28]
0x180034195  add     rsp, 48h
0x180034199  pop     r14
0x18003419b  pop     r13
0x18003419d  pop     rdi
0x18003419e  pop     rsi
0x18003419f  pop     rbx
0x1800341a0  pop     rbp
0x1800341a1  retn
0x1800341a2  call    cs:__imp_GetLastError
0x1800341a8  cmp     [rbp+arg_38], 0
0x1800341ac  jz      loc_180034251
0x1800341b2  cmp     eax, 3
0x1800341b5  jnz     loc_180034251
0x1800341bb  mov     rcx, rbx; unsigned __int16 *
0x1800341be  call    ?CreateAllFolders@StreamHelper@@SAJPEBG@Z; StreamHelper::CreateAllFolders(ushort const *)
0x1800341c3  mov     [rbp+arg_28], eax
0x1800341c6  test    eax, eax
0x1800341c8  js      loc_1800342F3
0x1800341ce  mov     eax, [rbp+arg_20]
0x1800341d1  xor     r9d, r9d; lpSecurityAttributes
0x1800341d4  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1800341dd  mov     r8d, esi; dwShareMode
0x1800341e0  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800341e8  mov     edx, r14d; dwDesiredAccess
0x1800341eb  mov     rcx, rbx; lpFileName
0x1800341ee  mov     [rsp+48h+dwCreationDisposition], eax; dwCreationDisposition
0x1800341f2  call    cs:__imp_CreateFileW
0x1800341f8  mov     rdi, rax
0x1800341fb  cmp     rax, r13
0x1800341fe  jz      short loc_180034209
0x180034200  mov     [rbp+arg_28], 0
0x180034207  jmp     short loc_18003418B
0x180034209  call    cs:__imp_GetLastError
0x18003420f  mov     ecx, eax
0x180034211  test    eax, eax
0x180034213  jle     short loc_18003421E
0x180034215  movzx   ecx, ax
0x180034218  or      ecx, 80070000h
0x18003421e  mov     edx, 80000000h
0x180034223  mov     [rbp+arg_28], ecx
0x180034226  lea     eax, [rcx+rdx]
0x180034229  test    edx, eax
0x18003422b  jnz     loc_18003418B
0x180034231  cmp     ecx, 80070002h
0x180034237  jz      loc_18003418B
0x18003423d  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits, 20h
0x180034244  jz      loc_18003418B
0x18003424a  call    ?_t_address@@YAPEAXXZ; _t_address(void)
0x18003424f  jmp     short loc_180034272
0x180034251  test    eax, eax
0x180034253  jle     short loc_18003425D
0x180034255  movzx   eax, ax
0x180034258  or      eax, 80070000h
0x18003425d  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits, 20h
0x180034264  mov     [rbp+arg_28], eax
0x180034267  jz      loc_18003418B
0x18003426d  call    ?_t_address@@YAPEAXXZ; _t_address(void)
0x180034272  mov     [rsp+48h+var_10], r13
0x180034277  lea     rcx, _ETWMESSAGE; EventDescriptor
0x18003427e  mov     rdx, rax; void *
0x180034281  mov     [rsp+48h+hTemplateFile], 0
0x18003428a  lea     rax, [rbp+arg_28]
0x18003428e  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 4
0x180034297  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18003429e  mov     qword ptr [rsp+48h+dwCreationDisposition], rax
0x1800342a3  mov     r8, rbx
0x1800342a6  call    ?EtwTraceMessage@@YAXPEBU_EVENT_DESCRIPTOR@@PEAXZZ; EtwTraceMessage(_EVENT_DESCRIPTOR const *,void *,...)
0x1800342ab  jmp     loc_18003418B
0x1800342b0  call    ?_t_address@@YAPEAXXZ; _t_address(void)
0x1800342b5  mov     [rsp+48h+var_10], r13
0x1800342ba  lea     rcx, _ETWMESSAGE; EventDescriptor
0x1800342c1  mov     rdx, rax; void *
0x1800342c4  mov     [rsp+48h+hTemplateFile], 0
0x1800342cd  lea     rax, [rbp+arg_20]
0x1800342d1  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], 4
0x1800342da  mov     r9, 0FFFFFFFFFFFFFFFEh
0x1800342e1  mov     qword ptr [rsp+48h+dwCreationDisposition], rax
0x1800342e6  mov     r8, rbx
0x1800342e9  call    ?EtwTraceMessage@@YAXPEBU_EVENT_DESCRIPTOR@@PEAXZZ; EtwTraceMessage(_EVENT_DESCRIPTOR const *,void *,...)
0x1800342ee  jmp     loc_180034159
0x1800342f3  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits, 20h
0x1800342fa  jz      loc_18003418B
0x180034300  call    ?_t_address@@YAPEAXXZ; _t_address(void)
0x180034305  jmp     loc_180034272
```
