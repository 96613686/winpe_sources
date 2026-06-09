# CheckUnZippedFile(HWND__ *,ushort const *,ushort const *,ushort const *)

- ea: `0x180022ffc`
- end: `0x18002315b`
- name: `?CheckUnZippedFile@@YAJPEAUHWND__@@PEBG11@Z`
- size: `351`
- prototype: `int(HWND, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001ea30`
- `0x18001f284`

## callees

- `0x180022ffc`
- `0x180036f50`
- `0x1800405b4`
- `0x180071010`

## import_xrefs

- `SHLWAPI!PathCombineW` at `0x180023042`
- `SHLWAPI!PathCombineW` at `0x180023042`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023074`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023074`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180023130`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180023130`

## pseudocode

```c
__int64 __fastcall CheckUnZippedFile(
        HWND a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  unsigned int v8; // ebx
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  int v12; // eax
  struct _EVENT_DATA_DESCRIPTOR ppv; // [rsp+30h] [rbp-258h] BYREF
  WCHAR pszDest[264]; // [rsp+40h] [rbp-248h] BYREF

  if ( (Microsoft_Windows_Shell_ZipFolderEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer((int)a1, (int)&ShellTraceId_ZipFolder_AESCheck_Start, (int)a3, (int)a4, &ppv);
  v8 = 0;
  if ( PathCombineW(pszDest, a3, a4) )
  {
    ppv.Ptr = 0;
    if ( CoCreateInstance(&CLSID_AttachmentServices, 0, 1u, &GUID_4f2b781f_a608_4543_abf0_49c246ebbba9, (LPVOID *)&ppv) >= 0 )
    {
      if ( (*(int (__fastcall **)(ULONGLONG, WCHAR *))(*(_QWORD *)ppv.Ptr + 40LL))(ppv.Ptr, pszDest) >= 0
        && (*(int (__fastcall **)(ULONGLONG, const unsigned __int16 *))(*(_QWORD *)ppv.Ptr + 64LL))(ppv.Ptr, a2) >= 0 )
      {
        v12 = (*(__int64 (__fastcall **)(ULONGLONG, HWND))(*(_QWORD *)ppv.Ptr + 128LL))(ppv.Ptr, a1);
        v8 = v12;
        if ( v12 == 1 )
        {
          v8 = 0;
        }
        else if ( v12 < 0 )
        {
          DeleteFileW(pszDest);
          if ( a1 )
            v8 = -2147023673;
        }
      }
      (*(void (__fastcall **)(ULONGLONG))(*(_QWORD *)ppv.Ptr + 16LL))(ppv.Ptr);
    }
  }
  if ( (Microsoft_Windows_Shell_ZipFolderEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v9, (int)&ShellTraceId_ZipFolder_AESCheck_Stop, v10, v11, &ppv);
  return v8;
}

```

## disassembly

```asm
0x180022ffc  push    rbx
0x180022ffe  push    rbp
0x180022fff  push    rsi
0x180023000  push    rdi
0x180023001  push    r14
0x180023003  sub     rsp, 260h
0x18002300a  mov     rax, cs:__security_cookie
0x180023011  xor     rax, rsp
0x180023014  mov     [rsp+288h+var_38], rax
0x18002301c  test    cs:Microsoft_Windows_Shell_ZipFolderEnableBits, 1
0x180023023  mov     rbp, r9
0x180023026  mov     rsi, r8
0x180023029  mov     r14, rdx
0x18002302c  mov     rdi, rcx
0x18002302f  jnz     loc_18002310C
0x180023035  mov     r8, rbp; pszFile
0x180023038  lea     rcx, [rsp+288h+pszDest]; pszDest
0x18002303d  mov     rdx, rsi; pszDir
0x180023040  xor     ebx, ebx
0x180023042  call    cs:__imp_PathCombineW
0x180023048  test    rax, rax
0x18002304b  jz      loc_1800230E3
0x180023051  lea     rax, [rsp+288h+var_258]
0x180023056  mov     [rsp+288h+var_258.Ptr], rbx
0x18002305b  lea     r9, _GUID_4f2b781f_a608_4543_abf0_49c246ebbba9; riid
0x180023062  mov     [rsp+288h+ppv], rax; ppv
0x180023067  xor     edx, edx; pUnkOuter
0x180023069  lea     r8d, [rbx+1]; dwClsContext
0x18002306d  lea     rcx, CLSID_AttachmentServices; rclsid
0x180023074  call    cs:__imp_CoCreateInstance
0x18002307a  test    eax, eax
0x18002307c  js      short loc_1800230E3
0x18002307e  mov     rcx, [rsp+288h+var_258.Ptr]
0x180023083  lea     rdx, [rsp+288h+pszDest]
0x180023088  mov     rax, [rcx]
0x18002308b  mov     rax, [rax+28h]
0x18002308f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023094  test    eax, eax
0x180023096  js      short loc_1800230D2
0x180023098  mov     rcx, [rsp+288h+var_258.Ptr]
0x18002309d  mov     rdx, r14
0x1800230a0  mov     rax, [rcx]
0x1800230a3  mov     rax, [rax+40h]
0x1800230a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230ac  test    eax, eax
0x1800230ae  js      short loc_1800230D2
0x1800230b0  mov     rcx, [rsp+288h+var_258.Ptr]
0x1800230b5  mov     rdx, rdi
0x1800230b8  mov     rax, [rcx]
0x1800230bb  mov     rax, [rax+80h]
0x1800230c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230c7  mov     ebx, eax
0x1800230c9  cmp     eax, 1
0x1800230cc  jz      short loc_180023127
0x1800230ce  test    eax, eax
0x1800230d0  js      short loc_18002312B
0x1800230d2  mov     rcx, [rsp+288h+var_258.Ptr]
0x1800230d7  mov     rax, [rcx]
0x1800230da  mov     rax, [rax+10h]
0x1800230de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230e3  test    cs:Microsoft_Windows_Shell_ZipFolderEnableBits, 1
0x1800230ea  jnz     short loc_180023143
0x1800230ec  mov     eax, ebx
0x1800230ee  mov     rcx, [rsp+288h+var_38]
0x1800230f6  xor     rcx, rsp; StackCookie
0x1800230f9  call    __security_check_cookie
0x1800230fe  add     rsp, 260h
0x180023105  pop     r14
0x180023107  pop     rdi
0x180023108  pop     rsi
0x180023109  pop     rbp
0x18002310a  pop     rbx
0x18002310b  retn
0x18002310c  lea     rax, [rsp+288h+var_258]
0x180023111  lea     rdx, ShellTraceId_ZipFolder_AESCheck_Start; int
0x180023118  mov     [rsp+288h+ppv], rax; PEVENT_DATA_DESCRIPTOR
0x18002311d  call    McGenEventWrite_EventWriteTransfer
0x180023122  jmp     loc_180023035
0x180023127  xor     ebx, ebx
0x180023129  jmp     short loc_1800230D2
0x18002312b  lea     rcx, [rsp+288h+pszDest]; lpFileName
0x180023130  call    cs:__imp_DeleteFileW
0x180023136  test    rdi, rdi
0x180023139  mov     eax, 800704C7h
0x18002313e  cmovnz  ebx, eax
0x180023141  jmp     short loc_1800230D2
0x180023143  lea     rax, [rsp+288h+var_258]
0x180023148  lea     rdx, ShellTraceId_ZipFolder_AESCheck_Stop; int
0x18002314f  mov     [rsp+288h+ppv], rax; PEVENT_DATA_DESCRIPTOR
0x180023154  call    McGenEventWrite_EventWriteTransfer
0x180023159  jmp     short loc_1800230EC
```
