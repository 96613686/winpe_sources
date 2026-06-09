# CWiaLog::InitializeLogEx(uchar *)

- ea: `0x180074440`
- end: `0x180074508`
- name: `?InitializeLogEx@CWiaLog@@EEAAJPEAE@Z`
- size: `200`
- prototype: `__int64 __fastcall(CWiaLog *this, unsigned __int8 *, __int64, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting`

## callees

- `0x180010d78`
- `0x18002f290`
- `0x1800742a8`
- `0x180074440`
- `0x1800745cc`
- `0x180074758`
- `0x1800749d0`
- `0x180074c84`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800744d4`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800744d4`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800744de`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800744de`

## string_xrefs

- `0x180074466`: `noname.dll`

## pseudocode

```c
__int64 __fastcall CWiaLog::InitializeLogEx(CWiaLog *this, unsigned __int8 *a2, __int64 a3, int a4)
{
  unsigned __int16 *v4; // rbp
  CWiaLog *v6; // rdi
  unsigned int v7; // esi

  v4 = (unsigned __int16 *)((char *)this + 48);
  v6 = (CWiaLog *)((char *)this - 8);
  v7 = 0;
  *((_QWORD *)this + 5) = a2;
  if ( !CWiaLog::FormatDLLName(this, (HINSTANCE)a2, (unsigned __int16 *)this + 24, a4) )
  {
    StringCbCopyW(v4, 0x80u, L"noname.dll");
    v7 = -2147024809;
  }
  StringCchCopyW((unsigned __int16 *)this + 354, 0x40u, v4);
  if ( (unsigned int)CWiaLog::OpenLogFile(v6) )
  {
    if ( *((_QWORD *)this + 4) )
    {
      CWiaLog::QueryLoggingSettings(v6);
      if ( *((_DWORD *)this + 730) )
        CWiaLog::ProcessTruncation(v6);
      if ( *((_DWORD *)this + 731) )
      {
        SetFilePointer(*((HANDLE *)this + 4), 0, 0, 0);
        SetEndOfFile(*((HANDLE *)this + 4));
      }
      CWiaLog::WriteLogSessionHeader(v6);
      *((_DWORD *)this + 209) = 1;
    }
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return v7;
}

```

## disassembly

```asm
0x180074440  push    rbx
0x180074442  push    rbp
0x180074443  push    rsi
0x180074444  push    rdi
0x180074445  sub     rsp, 28h
0x180074449  lea     rbp, [rcx+30h]
0x18007444d  mov     rbx, rcx
0x180074450  lea     rdi, [rcx-8]
0x180074454  mov     r8, rbp; unsigned __int16 *
0x180074457  xor     esi, esi
0x180074459  mov     [rdi+30h], rdx
0x18007445d  call    ?FormatDLLName@CWiaLog@@AEAAHPEAUHINSTANCE__@@PEAGH@Z; CWiaLog::FormatDLLName(HINSTANCE__ *,ushort *,int)
0x180074462  test    eax, eax
0x180074464  jnz     short loc_18007447F
0x180074466  lea     r8, aNonameDll; "noname.dll"
0x18007446d  mov     edx, 80h; unsigned __int64
0x180074472  mov     rcx, rbp; unsigned __int16 *
0x180074475  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18007447a  mov     esi, 80070057h
0x18007447f  lea     rcx, [rbx+2C4h]; unsigned __int16 *
0x180074486  mov     r8, rbp; unsigned __int16 *
0x180074489  mov     edx, 40h ; '@'; unsigned __int64
0x18007448e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180074493  mov     rcx, rdi; this
0x180074496  call    ?OpenLogFile@CWiaLog@@AEAAHXZ; CWiaLog::OpenLogFile(void)
0x18007449b  test    eax, eax
0x18007449d  jz      short loc_1800744F8
0x18007449f  cmp     qword ptr [rbx+20h], 0
0x1800744a4  jz      short loc_1800744FD
0x1800744a6  mov     rcx, rdi; this
0x1800744a9  call    ?QueryLoggingSettings@CWiaLog@@AEAAHXZ; CWiaLog::QueryLoggingSettings(void)
0x1800744ae  cmp     dword ptr [rbx+0B68h], 0
0x1800744b5  jz      short loc_1800744BF
0x1800744b7  mov     rcx, rdi; this
0x1800744ba  call    ?ProcessTruncation@CWiaLog@@AEAAXXZ; CWiaLog::ProcessTruncation(void)
0x1800744bf  cmp     dword ptr [rbx+0B6Ch], 0
0x1800744c6  jz      short loc_1800744E4
0x1800744c8  mov     rcx, [rbx+20h]; hFile
0x1800744cc  xor     r9d, r9d; dwMoveMethod
0x1800744cf  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800744d2  xor     edx, edx; lDistanceToMove
0x1800744d4  call    cs:__imp_SetFilePointer
0x1800744da  mov     rcx, [rbx+20h]; hFile
0x1800744de  call    cs:__imp_SetEndOfFile
0x1800744e4  mov     rcx, rdi; this
0x1800744e7  call    ?WriteLogSessionHeader@CWiaLog@@AEAAXXZ; CWiaLog::WriteLogSessionHeader(void)
0x1800744ec  mov     dword ptr [rbx+344h], 1
0x1800744f6  jmp     short loc_1800744FD
0x1800744f8  mov     esi, 80004005h
0x1800744fd  mov     eax, esi
0x1800744ff  add     rsp, 28h
0x180074503  pop     rdi
0x180074504  pop     rsi
0x180074505  pop     rbp
0x180074506  pop     rbx
0x180074507  retn
```
