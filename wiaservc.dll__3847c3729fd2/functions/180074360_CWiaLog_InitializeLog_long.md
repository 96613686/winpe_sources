# CWiaLog::InitializeLog(long)

- ea: `0x180074360`
- end: `0x180074433`
- name: `?InitializeLog@CWiaLog@@EEAAJJ@Z`
- size: `211`
- prototype: `__int64 __fastcall(CWiaLog *this, HINSTANCE, __int64, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting`

## callees

- `0x180010d78`
- `0x18002f290`
- `0x1800742a8`
- `0x180074360`
- `0x1800745cc`
- `0x180074758`
- `0x1800749d0`
- `0x180074c84`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800743f8`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800743f8`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180074402`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180074402`

## string_xrefs

- `0x18007438a`: `noname.dll`

## pseudocode

```c
__int64 __fastcall CWiaLog::InitializeLog(CWiaLog *this, HINSTANCE a2, __int64 a3, int a4)
{
  unsigned __int16 *v4; // rsi
  unsigned int v6; // edi

  v4 = (unsigned __int16 *)((char *)this + 56);
  *((_QWORD *)this + 6) = (unsigned int)a2;
  v6 = 0;
  if ( !CWiaLog::FormatDLLName(this, (HINSTANCE)(unsigned int)a2, (unsigned __int16 *)this + 28, a4) )
  {
    StringCbCopyW(v4, 0x80u, L"noname.dll");
    v6 = -2147024809;
  }
  StringCchCopyW((unsigned __int16 *)this + 358, 0x40u, v4);
  if ( (unsigned int)CWiaLog::OpenLogFile(this) )
  {
    if ( *((_QWORD *)this + 5) )
    {
      CWiaLog::QueryLoggingSettings(this);
      if ( *((_DWORD *)this + 732) )
        CWiaLog::ProcessTruncation(this);
      if ( *((_DWORD *)this + 733) )
      {
        SetFilePointer(*((HANDLE *)this + 5), 0, 0, 0);
        SetEndOfFile(*((HANDLE *)this + 5));
      }
      CWiaLog::WriteLogSessionHeader(this);
      *((_DWORD *)this + 211) = 1;
    }
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return v6;
}

```

## disassembly

```asm
0x180074360  mov     [rsp+arg_0], rbx
0x180074365  mov     [rsp+arg_8], rsi
0x18007436a  push    rdi
0x18007436b  sub     rsp, 20h
0x18007436f  lea     rsi, [rcx+38h]
0x180074373  mov     edx, edx; HINSTANCE
0x180074375  mov     r8, rsi; unsigned __int16 *
0x180074378  mov     [rcx+30h], rdx
0x18007437c  mov     rbx, rcx
0x18007437f  xor     edi, edi
0x180074381  call    ?FormatDLLName@CWiaLog@@AEAAHPEAUHINSTANCE__@@PEAGH@Z; CWiaLog::FormatDLLName(HINSTANCE__ *,ushort *,int)
0x180074386  test    eax, eax
0x180074388  jnz     short loc_1800743A3
0x18007438a  lea     r8, aNonameDll; "noname.dll"
0x180074391  mov     edx, 80h; unsigned __int64
0x180074396  mov     rcx, rsi; unsigned __int16 *
0x180074399  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18007439e  mov     edi, 80070057h
0x1800743a3  lea     rcx, [rbx+2CCh]; unsigned __int16 *
0x1800743aa  mov     r8, rsi; unsigned __int16 *
0x1800743ad  mov     edx, 40h ; '@'; unsigned __int64
0x1800743b2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800743b7  mov     rcx, rbx; this
0x1800743ba  call    ?OpenLogFile@CWiaLog@@AEAAHXZ; CWiaLog::OpenLogFile(void)
0x1800743bf  test    eax, eax
0x1800743c1  jz      short loc_18007441C
0x1800743c3  cmp     qword ptr [rbx+28h], 0
0x1800743c8  jz      short loc_180074421
0x1800743ca  mov     rcx, rbx; this
0x1800743cd  call    ?QueryLoggingSettings@CWiaLog@@AEAAHXZ; CWiaLog::QueryLoggingSettings(void)
0x1800743d2  cmp     dword ptr [rbx+0B70h], 0
0x1800743d9  jz      short loc_1800743E3
0x1800743db  mov     rcx, rbx; this
0x1800743de  call    ?ProcessTruncation@CWiaLog@@AEAAXXZ; CWiaLog::ProcessTruncation(void)
0x1800743e3  cmp     dword ptr [rbx+0B74h], 0
0x1800743ea  jz      short loc_180074408
0x1800743ec  mov     rcx, [rbx+28h]; hFile
0x1800743f0  xor     r9d, r9d; dwMoveMethod
0x1800743f3  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800743f6  xor     edx, edx; lDistanceToMove
0x1800743f8  call    cs:__imp_SetFilePointer
0x1800743fe  mov     rcx, [rbx+28h]; hFile
0x180074402  call    cs:__imp_SetEndOfFile
0x180074408  mov     rcx, rbx; this
0x18007440b  call    ?WriteLogSessionHeader@CWiaLog@@AEAAXXZ; CWiaLog::WriteLogSessionHeader(void)
0x180074410  mov     dword ptr [rbx+34Ch], 1
0x18007441a  jmp     short loc_180074421
0x18007441c  mov     edi, 80004005h
0x180074421  mov     rbx, [rsp+28h+arg_0]
0x180074426  mov     eax, edi
0x180074428  mov     rsi, [rsp+28h+arg_8]
0x18007442d  add     rsp, 20h
0x180074431  pop     rdi
0x180074432  retn
```
