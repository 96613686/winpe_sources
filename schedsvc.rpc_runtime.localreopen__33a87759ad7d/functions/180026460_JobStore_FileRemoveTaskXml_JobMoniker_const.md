# JobStore::FileRemoveTaskXml(JobMoniker const &)

- ea: `0x180026460`
- end: `0x1800265bd`
- name: `?FileRemoveTaskXml@JobStore@@QEBAJAEBVJobMoniker@@@Z`
- size: `349`
- prototype: `int(JobStore *__hidden this, const struct JobMoniker *)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18001fdb0`
- `0x1800213f8`
- `0x180045df0`

## callees

- `0x18001a260`
- `0x18002132c`
- `0x180026460`
- `0x1800265c4`
- `0x1800276c0`
- `0x180027ee0`
- `0x18003f270`
- `0x18003f3c0`
- `0x180056794`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800264f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026533`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800264f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026533`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180026529`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180026529`

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
0x180026460  mov     [rsp+arg_0], rbx
0x180026465  push    rdi
0x180026466  sub     rsp, 50h
0x18002646a  mov     rdi, rdx
0x18002646d  mov     rbx, rcx
0x180026470  call    ?GetUseXmlStore@JobStore@@QEBAEXZ; JobStore::GetUseXmlStore(void)
0x180026475  test    al, al
0x180026477  jnz     short loc_180026480
0x180026479  xor     eax, eax
0x18002647b  jmp     loc_1800265B2
0x180026480  mov     [rsp+58h+String2], 0
0x180026489  mov     rcx, rdi; this
0x18002648c  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x180026491  mov     rdx, rax
0x180026494  lea     r8, [rsp+58h+String2]
0x180026499  mov     rcx, rbx
0x18002649c  call    ?GetXmlFileSystemPath@JobStore@@QEBAJPEBGAEAV?$AutoVectorPtr@G@wmi@@@Z; JobStore::GetXmlFileSystemPath(ushort const *,wmi::AutoVectorPtr<ushort> &)
0x1800264a1  mov     ebx, eax
0x1800264a3  test    eax, eax
0x1800264a5  js      loc_1800265A6
0x1800264ab  xorps   xmm0, xmm0
0x1800264ae  movdqu  xmmword ptr [rsp+58h+hFile], xmm0
0x1800264b4  mov     [rsp+58h+var_30], 2000080h; unsigned int
0x1800264bc  mov     r8d, 3; unsigned int
0x1800264c2  mov     dword ptr [rsp+58h+var_38], r8d; struct _SECURITY_ATTRIBUTES *
0x1800264c7  xor     r9d, r9d; unsigned int
0x1800264ca  mov     edx, 10000h; unsigned __int16 *
0x1800264cf  mov     rcx, [rsp+58h+String2]; String2
0x1800264d4  call    ?CreateFileSafe@tsched@@YAPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; tsched::CreateFileSafe(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x1800264d9  mov     rdx, rax
0x1800264dc  lea     rcx, [rsp+58h+hFile]
0x1800264e1  call    ??4JobsAutoHandle@tsched@@QEAAAEAV01@PEAX@Z; tsched::JobsAutoHandle::operator=(void *)
0x1800264e6  mov     rcx, [rsp+58h+hFile]; hFile
0x1800264eb  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800264ef  jnz     short loc_180026515
0x1800264f1  call    cs:__imp_GetLastError
0x1800264f7  mov     ebx, eax
0x1800264f9  test    eax, eax
0x1800264fb  jle     short loc_180026506
0x1800264fd  movzx   ebx, ax
0x180026500  or      ebx, 80070000h
0x180026506  lea     rcx, [rsp+58h+hFile]; this
0x18002650b  call    ?Close@JobsAutoHandle@tsched@@QEAAXXZ; tsched::JobsAutoHandle::Close(void)
0x180026510  jmp     loc_1800265A6
0x180026515  mov     [rsp+58h+FileInformation], 1
0x18002651a  mov     r9d, 1; dwBufferSize
0x180026520  lea     r8, [rsp+58h+FileInformation]; lpFileInformation
0x180026525  lea     edx, [r9+3]; FileInformationClass
0x180026529  call    cs:__imp_SetFileInformationByHandle
0x18002652f  test    eax, eax
0x180026531  jnz     short loc_18002659A
0x180026533  call    cs:__imp_GetLastError
0x180026539  mov     ebx, eax
0x18002653b  test    eax, eax
0x18002653d  jle     short loc_180026548
0x18002653f  movzx   ebx, ax
0x180026542  or      ebx, 80070000h
0x180026548  lea     rcx, WPP_GLOBAL_Control
0x18002654f  mov     rax, cs:WPP_GLOBAL_Control
0x180026556  cmp     rax, rcx
0x180026559  jz      short loc_180026506
0x18002655b  test    dword ptr [rax+1Ch], 40000h
0x180026562  jz      short loc_180026506
0x180026564  cmp     byte ptr [rax+19h], 4
0x180026568  jb      short loc_180026506
0x18002656a  mov     rcx, rdi; this
0x18002656d  call    ?GetPath@JobMoniker@@QEBAPEBGXZ; JobMoniker::GetPath(void)
0x180026572  mov     edx, 4Ch ; 'L'
0x180026577  mov     dword ptr [rsp+58h+var_38], ebx
0x18002657b  mov     r9, rax
0x18002657e  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x180026585  mov     rcx, cs:WPP_GLOBAL_Control
0x18002658c  mov     rcx, [rcx+10h]
0x180026590  call    WPP_SF_Sd
0x180026595  jmp     loc_180026506
0x18002659a  lea     rcx, [rsp+58h+hFile]; this
0x18002659f  call    ?Close@JobsAutoHandle@tsched@@QEAAXXZ; tsched::JobsAutoHandle::Close(void)
0x1800265a4  xor     ebx, ebx
0x1800265a6  mov     rcx, [rsp+58h+String2]; void *
0x1800265ab  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800265b0  mov     eax, ebx
0x1800265b2  mov     rbx, [rsp+58h+arg_0]
0x1800265b7  add     rsp, 50h
0x1800265bb  pop     rdi
0x1800265bc  retn
```
