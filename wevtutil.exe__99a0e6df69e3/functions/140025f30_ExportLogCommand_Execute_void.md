# ExportLogCommand::Execute(void)

- ea: `0x140025f30`
- end: `0x140026052`
- name: `?Execute@ExportLogCommand@@UEAAXXZ`
- size: `290`
- prototype: `void __fastcall(ExportLogCommand *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140010450`
- `0x140022cec`
- `0x140025f30`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025fb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025fb5`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtExportLog` at `0x140025fa7`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtExportLog` at `0x140025fa7`

## pseudocode

```c
void __fastcall ExportLogCommand::Execute(ExportLogCommand *this)
{
  DWORD v1; // eax
  const WCHAR *v2; // r9
  const WCHAR *v3; // r8
  char *Src; // rbx
  const WCHAR *v5; // rdx
  DWORD LastError; // edi
  const char *Flags; // [rsp+20h] [rbp-58h]
  _BYTE pExceptionObject[56]; // [rsp+40h] [rbp-38h] BYREF

  v1 = ((*((_BYTE *)this + 136) != 0) + 1) | 0x2000;
  if ( !*((_BYTE *)this + 138) )
    v1 = (*((_BYTE *)this + 136) != 0) + 1;
  if ( *((_QWORD *)this + 15) )
  {
    v2 = (const WCHAR *)((char *)this + 104);
    if ( *((_QWORD *)this + 16) > 7u )
      v2 = *(const WCHAR **)v2;
  }
  else
  {
    v2 = 0;
  }
  if ( *((_QWORD *)this + 11) )
  {
    v3 = (const WCHAR *)((char *)this + 72);
    if ( *((_QWORD *)this + 12) > 7u )
      v3 = *(const WCHAR **)v3;
  }
  else
  {
    v3 = 0;
  }
  Src = (char *)this + 40;
  if ( *((_QWORD *)this + 8) <= 7u )
    v5 = (const WCHAR *)((char *)this + 40);
  else
    v5 = *(const WCHAR **)Src;
  if ( !EvtExportLog(*((EVT_HANDLE *)this + 3), v5, v3, v2, v1) )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_86b388a84c2d3f26078be78498fb4b90_Traceguids, LastError);
    }
    if ( *((_QWORD *)Src + 3) > 7u )
      Src = *(char **)Src;
    EvtException::EvtException(
      (EvtException *)pExceptionObject,
      LastError,
      0,
      0,
      Flags,
      70,
      0x3Au,
      (const wchar_t *)Src);
    throw (EvtException *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x140025f30  mov     [rsp+arg_0], rbx
0x140025f35  push    rdi
0x140025f36  sub     rsp, 70h
0x140025f3a  mov     al, [rcx+88h]
0x140025f40  neg     al
0x140025f42  sbb     edx, edx
0x140025f44  neg     edx
0x140025f46  inc     edx
0x140025f48  mov     eax, edx
0x140025f4a  bts     eax, 0Dh
0x140025f4e  cmp     byte ptr [rcx+8Ah], 0
0x140025f55  cmovz   eax, edx
0x140025f58  cmp     qword ptr [rcx+78h], 0
0x140025f5d  jbe     short loc_140025F6F
0x140025f5f  lea     r9, [rcx+68h]
0x140025f63  cmp     qword ptr [r9+18h], 7
0x140025f68  jbe     short loc_140025F72
0x140025f6a  mov     r9, [r9]
0x140025f6d  jmp     short loc_140025F72
0x140025f6f  xor     r9d, r9d; TargetFilePath
0x140025f72  cmp     qword ptr [rcx+58h], 0
0x140025f77  jbe     short loc_140025F89
0x140025f79  lea     r8, [rcx+48h]
0x140025f7d  cmp     qword ptr [r8+18h], 7
0x140025f82  jbe     short loc_140025F8C
0x140025f84  mov     r8, [r8]
0x140025f87  jmp     short loc_140025F8C
0x140025f89  xor     r8d, r8d; Query
0x140025f8c  lea     rbx, [rcx+28h]
0x140025f90  cmp     qword ptr [rbx+18h], 7
0x140025f95  jbe     short loc_140025F9C
0x140025f97  mov     rdx, [rbx]
0x140025f9a  jmp     short loc_140025F9F
0x140025f9c  mov     rdx, rbx; Path
0x140025f9f  mov     rcx, [rcx+18h]; Session
0x140025fa3  mov     dword ptr [rsp+78h+Flags], eax; char *
0x140025fa7  call    cs:__imp_EvtExportLog
0x140025fad  test    eax, eax
0x140025faf  jnz     loc_140026044
0x140025fb5  call    cs:__imp_GetLastError
0x140025fbb  mov     edi, eax
0x140025fbd  mov     eax, 507h
0x140025fc2  test    edi, edi
0x140025fc4  cmovz   edi, eax
0x140025fc7  mov     rcx, cs:WPP_GLOBAL_Control
0x140025fce  lea     rax, WPP_GLOBAL_Control
0x140025fd5  cmp     rcx, rax
0x140025fd8  jz      short loc_140026001
0x140025fda  test    dword ptr [rcx+1Ch], 400000h
0x140025fe1  jz      short loc_140026001
0x140025fe3  cmp     byte ptr [rcx+19h], 2
0x140025fe7  jb      short loc_140026001
0x140025fe9  mov     rcx, [rcx+10h]
0x140025fed  lea     r8, WPP_86b388a84c2d3f26078be78498fb4b90_Traceguids
0x140025ff4  mov     edx, 0Dh
0x140025ff9  mov     r9d, edi
0x140025ffc  call    WPP_SF_d
0x140026001  cmp     qword ptr [rbx+18h], 7
0x140026006  jbe     short loc_14002600B
0x140026008  mov     rbx, [rbx]
0x14002600b  mov     [rsp+78h+Src], rbx; Src
0x140026010  lea     rcx, [rsp+78h+pExceptionObject]; this
0x140026015  mov     [rsp+78h+var_48], 3Ah ; ':'; unsigned int
0x14002601d  xor     r9d, r9d; unsigned int
0x140026020  xor     r8d, r8d; unsigned int
0x140026023  mov     [rsp+78h+var_50], 46h ; 'F'; int
0x14002602b  mov     edx, edi; unsigned int
0x14002602d  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x140026032  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140026039  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x14002603e  call    _CxxThrowException_0
0x140026044  mov     rbx, [rsp+78h+arg_0]
0x14002604c  add     rsp, 70h
0x140026050  pop     rdi
0x140026051  retn
```
