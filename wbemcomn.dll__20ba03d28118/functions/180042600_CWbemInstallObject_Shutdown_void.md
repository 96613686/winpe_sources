# CWbemInstallObject::Shutdown(void)

- ea: `0x180042600`
- end: `0x180042694`
- name: `?Shutdown@CWbemInstallObject@@SAXXZ`
- size: `148`
- prototype: `void(void)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callees

- `0x180042600`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004264a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004264a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042638`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042638`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180042665`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180042665`

## string_xrefs

- `0x180042631`: `DllCanUnloadNow`

## pseudocode

```c
void CWbemInstallObject::Shutdown(void)
{
  __int64 v0; // rbx
  HMODULE v1; // rcx
  __int64 (*ProcAddress)(void); // rax
  unsigned int v3; // eax
  signed int LastError; // eax
  bool v5; // zf

  if ( CWbemInstallObject::m_bOffline )
  {
    v0 = 0;
    while ( 1 )
    {
      v1 = (HMODULE)qword_180068308[2 * v0];
      if ( v1 )
        break;
LABEL_11:
      if ( ++v0 == 5 )
      {
        CWbemInstallObject::m_bOffline = 0;
        return;
      }
    }
    ProcAddress = GetProcAddress(v1, "DllCanUnloadNow");
    if ( ProcAddress )
    {
      v3 = ProcAddress();
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError == 0;
      if ( LastError <= 0 )
        goto LABEL_9;
      v3 = (unsigned __int16)LastError | 0x80070000;
    }
    v5 = v3 == 0;
LABEL_9:
    if ( v5 )
    {
      FreeLibrary((HMODULE)qword_180068308[2 * v0]);
      qword_180068308[2 * v0] = 0;
    }
    goto LABEL_11;
  }
}

```

## disassembly

```asm
0x180042600  mov     [rsp+arg_0], rbx
0x180042605  mov     [rsp+arg_8], rbp
0x18004260a  push    rdi
0x18004260b  sub     rsp, 20h
0x18004260f  cmp     cs:?m_bOffline@CWbemInstallObject@@0_NA, 0; bool CWbemInstallObject::m_bOffline
0x180042616  jz      short loc_180042684
0x180042618  xor     ebx, ebx
0x18004261a  mov     rdi, rbx
0x18004261d  lea     rbp, qword_180068308
0x180042624  add     rdi, rdi
0x180042627  mov     rcx, [rbp+rdi*8+0]; hModule
0x18004262c  test    rcx, rcx
0x18004262f  jz      short loc_180042674
0x180042631  lea     rdx, aDllcanunloadno; "DllCanUnloadNow"
0x180042638  call    cs:__imp_GetProcAddress
0x18004263e  test    rax, rax
0x180042641  jz      short loc_18004264A
0x180042643  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042648  jmp     short loc_18004265C
0x18004264a  call    cs:__imp_GetLastError
0x180042650  test    eax, eax
0x180042652  jle     short loc_18004265E
0x180042654  movzx   eax, ax
0x180042657  or      eax, 80070000h
0x18004265c  test    eax, eax
0x18004265e  jnz     short loc_180042674
0x180042660  mov     rcx, [rbp+rdi*8+0]; hLibModule
0x180042665  call    cs:__imp_FreeLibrary
0x18004266b  mov     qword ptr [rbp+rdi*8+0], 0
0x180042674  inc     rbx
0x180042677  cmp     rbx, 5
0x18004267b  jnz     short loc_18004261A
0x18004267d  mov     cs:?m_bOffline@CWbemInstallObject@@0_NA, 0; bool CWbemInstallObject::m_bOffline
0x180042684  mov     rbx, [rsp+28h+arg_0]
0x180042689  mov     rbp, [rsp+28h+arg_8]
0x18004268e  add     rsp, 20h
0x180042692  pop     rdi
0x180042693  retn
```
