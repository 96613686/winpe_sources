# JobStore::FileRemoveTaskXml(JobMoniker const &)

- ea: `0x180021260`
- end: `0x1800213d0`
- name: `?FileRemoveTaskXml@JobStore@@QEBAJAEBVJobMoniker@@@Z`
- size: `368`
- prototype: `int(JobStore *__hidden this, const struct JobMoniker *)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18001d7ac`
- `0x18002c470`
- `0x180047ee0`

## callees

- `0x18000cc40`
- `0x180021260`
- `0x1800213d8`
- `0x1800229a0`
- `0x180022d80`
- `0x18002db74`
- `0x180040bf0`
- `0x180040dd0`
- `0x180059140`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800212f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002133f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800212f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002133f`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18002132f`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18002132f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall JobStore::FileRemoveTaskXml(JobStore *this, const struct JobMoniker *a2)
{
  unsigned __int16 *Path; // rax
  int XmlFileSystemPath; // ebx
  __int64 FileSafe; // rax
  signed int LastError; // eax
  signed int v9; // eax
  unsigned int v10; // eax
  struct _SECURITY_ATTRIBUTES *v11; // [rsp+20h] [rbp-38h]
  HANDLE hFile[3]; // [rsp+40h] [rbp-18h] BYREF
  char FileInformation; // [rsp+70h] [rbp+18h] BYREF
  wchar_t *String2; // [rsp+78h] [rbp+20h] BYREF

  if ( !JobStore::GetUseXmlStore(this) )
    return 0;
  String2 = 0;
  Path = (unsigned __int16 *)JobMoniker::GetPath(a2);
  XmlFileSystemPath = JobStore::GetXmlFileSystemPath((WCHAR **)this, Path, (LPVOID *)&String2);
  if ( XmlFileSystemPath >= 0 )
  {
    *(_OWORD *)hFile = 0;
    LODWORD(v11) = 3;
    FileSafe = tsched::CreateFileSafe(String2, (const unsigned __int16 *)0x10000, 3u, 0, v11, 0x2000080u);
    tsched::JobsAutoHandle::operator=(hFile, FileSafe);
    if ( hFile[0] == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      XmlFileSystemPath = LastError;
      if ( LastError > 0 )
        XmlFileSystemPath = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      FileInformation = 1;
      if ( SetFileInformationByHandle(hFile[0], FileDispositionInfo, &FileInformation, 1u) )
      {
        tsched::JobsAutoHandle::Close((tsched::JobsAutoHandle *)hFile);
        XmlFileSystemPath = 0;
        goto LABEL_16;
      }
      v9 = GetLastError();
      XmlFileSystemPath = v9;
      if ( v9 > 0 )
        XmlFileSystemPath = (unsigned __int16)v9 | 0x80070000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v10 = (unsigned int)JobMoniker::GetPath(a2);
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          76,
          (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
          v10,
          XmlFileSystemPath);
      }
    }
    tsched::JobsAutoHandle::Close((tsched::JobsAutoHandle *)hFile);
  }
LABEL_16:
  operator delete(String2);
  return (unsigned int)XmlFileSystemPath;
}

```

## disassembly

```asm
0x180021260  mov     [rsp+arg_0], rbx
0x180021265  push    rdi
0x180021266  sub     rsp, 50h
0x18002126a  mov     rdi, rdx
0x18002126d  mov     rbx, rcx
0x180021270  call    ?GetUseXmlStore@JobStore@@QEBAEXZ; JobStore::GetUseXmlStore(void)
0x180021275  test    al, al
0x180021277  jnz     short loc_180021280
0x180021279  xor     eax, eax
0x18002127b  jmp     loc_1800213C4
0x180021280  mov     [rsp+58h+String2], 0
0x180021289  mov     rcx, rdi; this
0x18002128c  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x180021291  mov     rdx, rax
0x180021294  lea     r8, [rsp+58h+String2]
0x180021299  mov     rcx, rbx
0x18002129c  call    ?GetXmlFileSystemPath@JobStore@@QEBAJPEBGAEAV?$AutoVectorPtr@G@wmi@@@Z; JobStore::GetXmlFileSystemPath(ushort const *,wmi::AutoVectorPtr<ushort> &)
0x1800212a1  mov     ebx, eax
0x1800212a3  test    eax, eax
0x1800212a5  js      loc_1800213B8
0x1800212ab  xorps   xmm0, xmm0
0x1800212ae  movdqu  xmmword ptr [rsp+58h+hFile], xmm0
0x1800212b4  mov     [rsp+58h+var_30], 2000080h; unsigned int
0x1800212bc  mov     r8d, 3; unsigned int
0x1800212c2  mov     dword ptr [rsp+58h+var_38], r8d; struct _SECURITY_ATTRIBUTES *
0x1800212c7  xor     r9d, r9d; unsigned int
0x1800212ca  mov     edx, 10000h; unsigned __int16 *
0x1800212cf  mov     rcx, [rsp+58h+String2]; String2
0x1800212d4  call    ?CreateFileSafe@tsched@@YAPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; tsched::CreateFileSafe(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x1800212d9  mov     rdx, rax
0x1800212dc  lea     rcx, [rsp+58h+hFile]
0x1800212e1  call    ??4JobsAutoHandle@tsched@@QEAAAEAV01@PEAX@Z; tsched::JobsAutoHandle::operator=(void *)
0x1800212e6  mov     rcx, [rsp+58h+hFile]; hFile
0x1800212eb  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800212ef  jnz     short loc_18002131B
0x1800212f1  call    cs:__imp_GetLastError
0x1800212f8  nop     dword ptr [rax+rax+00h]
0x1800212fd  mov     ebx, eax
0x1800212ff  test    eax, eax
0x180021301  jle     short loc_18002130C
0x180021303  movzx   ebx, ax
0x180021306  or      ebx, 80070000h
0x18002130c  lea     rcx, [rsp+58h+hFile]; this
0x180021311  call    ?Close@JobsAutoHandle@tsched@@QEAAXXZ; tsched::JobsAutoHandle::Close(void)
0x180021316  jmp     loc_1800213B8
0x18002131b  mov     [rsp+58h+FileInformation], 1
0x180021320  mov     r9d, 1; dwBufferSize
0x180021326  lea     r8, [rsp+58h+FileInformation]; lpFileInformation
0x18002132b  lea     edx, [r9+3]; FileInformationClass
0x18002132f  call    cs:__imp_SetFileInformationByHandle
0x180021336  nop     dword ptr [rax+rax+00h]
0x18002133b  test    eax, eax
0x18002133d  jnz     short loc_1800213AC
0x18002133f  call    cs:__imp_GetLastError
0x180021346  nop     dword ptr [rax+rax+00h]
0x18002134b  mov     ebx, eax
0x18002134d  test    eax, eax
0x18002134f  jle     short loc_18002135A
0x180021351  movzx   ebx, ax
0x180021354  or      ebx, 80070000h
0x18002135a  lea     rcx, WPP_GLOBAL_Control
0x180021361  mov     rax, cs:WPP_GLOBAL_Control
0x180021368  cmp     rax, rcx
0x18002136b  jz      short loc_18002130C
0x18002136d  test    dword ptr [rax+1Ch], 40000h
0x180021374  jz      short loc_18002130C
0x180021376  cmp     byte ptr [rax+19h], 4
0x18002137a  jb      short loc_18002130C
0x18002137c  mov     rcx, rdi; this
0x18002137f  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x180021384  mov     edx, 4Ch ; 'L'
0x180021389  mov     dword ptr [rsp+58h+var_38], ebx
0x18002138d  mov     r9, rax
0x180021390  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x180021397  mov     rcx, cs:WPP_GLOBAL_Control
0x18002139e  mov     rcx, [rcx+10h]
0x1800213a2  call    WPP_SF_Sd
0x1800213a7  jmp     loc_18002130C
0x1800213ac  lea     rcx, [rsp+58h+hFile]; this
0x1800213b1  call    ?Close@JobsAutoHandle@tsched@@QEAAXXZ; tsched::JobsAutoHandle::Close(void)
0x1800213b6  xor     ebx, ebx
0x1800213b8  mov     rcx, [rsp+58h+String2]; void *
0x1800213bd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800213c2  mov     eax, ebx
0x1800213c4  mov     rbx, [rsp+58h+arg_0]
0x1800213c9  add     rsp, 50h
0x1800213cd  pop     rdi
0x1800213ce  retn
```
