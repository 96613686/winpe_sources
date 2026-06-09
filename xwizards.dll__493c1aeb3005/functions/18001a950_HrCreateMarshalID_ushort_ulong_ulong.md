# HrCreateMarshalID(ushort *,ulong,ulong)

- ea: `0x18001a950`
- end: `0x18001abdc`
- name: `?HrCreateMarshalID@@YAJPEAGKK@Z`
- size: `652`
- prototype: `int(unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800163c0`
- `0x18002d1d0`
- `0x18002dee4`
- `0x18002f0d8`

## callees

- `0x180004370`
- `0x18000ae04`
- `0x18000e4ec`
- `0x18000e820`
- `0x18001a950`
- `0x18001b434`
- `0x18001b930`
- `0x180032a02`
- `0x180032a30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001aaa5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001aaa5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001aa59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001aaf4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001aa59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001aaf4`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001aa44`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001aa44`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001a9db`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001a9db`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001aa8d`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001aa8d`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomA` at `0x18001aad9`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomA` at `0x18001aad9`

## pseudocode

```c
__int64 __fastcall HrCreateMarshalID(unsigned __int16 *a1, unsigned int a2, int a3)
{
  HANDLE FileMappingW; // rax
  void *v8; // rbx
  unsigned int v9; // eax
  unsigned int LastErrorHRESULT; // edi
  PVOID *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  const void *v14; // rax
  DWORD CurrentProcessId; // eax
  ATOM v16; // ax
  int v17; // edx
  int v18; // r8d
  int v19; // eax
  CHAR String[256]; // [rsp+40h] [rbp-128h] BYREF

  if ( !a1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_57b06483306a3a4d34d88419a088456d_Traceguids, 2147942487LL);
    return 2147942487LL;
  }
  *a1 = 0;
  FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, 0x10u, 0);
  v8 = FileMappingW;
  if ( FileMappingW )
  {
    v14 = MapViewOfFile(FileMappingW, 2u, 0, 0, 0);
    if ( v14 )
    {
      UnmapViewOfFile(v14);
      memset_0(String, 0, 0xFFu);
      CurrentProcessId = GetCurrentProcessId();
      sprintf_sfn(String, 0xFFu, "%u:%u:%u:%p", 16, CurrentProcessId, a3, v8);
      v16 = GlobalAddAtomA(String);
      *a1 = v16;
      if ( v16 )
      {
        v11 = (PVOID *)WPP_GLOBAL_Control;
        LastErrorHRESULT = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          WPP_SF_DsD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, v18, v16, (__int64)String, 0);
          v11 = (PVOID *)WPP_GLOBAL_Control;
        }
        goto LABEL_25;
      }
      LastErrorHRESULT = GetLastErrorHRESULT();
      CloseHandle(v8);
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          (unsigned int)&WPP_57b06483306a3a4d34d88419a088456d_Traceguids,
          (unsigned int)String,
          LastErrorHRESULT);
        goto LABEL_19;
      }
    }
    else
    {
      LastErrorHRESULT = GetLastErrorHRESULT();
      CloseHandle(v8);
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v12 = 30;
        v13 = LastErrorHRESULT;
        goto LABEL_10;
      }
    }
  }
  else
  {
    v9 = GetLastErrorHRESULT();
    LastErrorHRESULT = v9;
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v12 = 29;
      v13 = v9;
LABEL_10:
      WPP_SF_d(v11[2], v12, &WPP_57b06483306a3a4d34d88419a088456d_Traceguids, v13);
LABEL_19:
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( (LastErrorHRESULT & 0x80000000) == 0 )
  {
LABEL_25:
    if ( a2 )
    {
      v19 = HrResizeMarshalID(*a1, a2);
      v11 = (PVOID *)WPP_GLOBAL_Control;
      LastErrorHRESULT = v19;
    }
  }
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 0x10) != 0 )
    WPP_SF_d(v11[2], 33, &WPP_57b06483306a3a4d34d88419a088456d_Traceguids, LastErrorHRESULT);
  return LastErrorHRESULT;
}

```

## disassembly

```asm
0x18001a950  mov     [rsp+arg_18], rbx
0x18001a955  push    rbp
0x18001a956  push    rdi
0x18001a957  push    r14
0x18001a959  sub     rsp, 150h
0x18001a960  mov     rax, cs:__security_cookie
0x18001a967  xor     rax, rsp
0x18001a96a  mov     [rsp+168h+var_28], rax
0x18001a972  mov     edi, r8d
0x18001a975  mov     ebp, edx
0x18001a977  mov     r14, rcx
0x18001a97a  test    rcx, rcx
0x18001a97d  jnz     short loc_18001A9BC
0x18001a97f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a986  lea     rbx, WPP_GLOBAL_Control
0x18001a98d  cmp     rcx, rbx
0x18001a990  jz      short loc_18001A9B2
0x18001a992  test    byte ptr [rcx+1Ch], 4
0x18001a996  jz      short loc_18001A9B2
0x18001a998  mov     rcx, [rcx+10h]
0x18001a99c  lea     edx, [r14+1Ch]
0x18001a9a0  mov     r9d, 80070057h
0x18001a9a6  lea     r8, WPP_57b06483306a3a4d34d88419a088456d_Traceguids
0x18001a9ad  call    WPP_SF_d
0x18001a9b2  mov     eax, 80070057h
0x18001a9b7  jmp     loc_18001ABB8
0x18001a9bc  xor     eax, eax
0x18001a9be  xor     r9d, r9d; dwMaximumSizeHigh
0x18001a9c1  mov     [rcx], ax
0x18001a9c4  xor     edx, edx; lpFileMappingAttributes
0x18001a9c6  mov     [rsp+168h+lpName], rax; lpName
0x18001a9cb  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18001a9cf  mov     [rsp+168h+dwMaximumSizeLow], 10h; dwMaximumSizeLow
0x18001a9d7  lea     r8d, [rax+4]; flProtect
0x18001a9db  call    cs:__imp_CreateFileMappingW
0x18001a9e1  mov     rbx, rax
0x18001a9e4  test    rax, rax
0x18001a9e7  jnz     short loc_18001AA2E
0x18001a9e9  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18001a9ee  mov     edi, eax
0x18001a9f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a9f7  lea     rbx, WPP_GLOBAL_Control
0x18001a9fe  cmp     rcx, rbx
0x18001aa01  jz      loc_18001AB38
0x18001aa07  test    byte ptr [rcx+1Ch], 4
0x18001aa0b  jz      loc_18001AB38
0x18001aa11  mov     edx, 1Dh
0x18001aa16  mov     r9d, eax
0x18001aa19  mov     rcx, [rcx+10h]
0x18001aa1d  lea     r8, WPP_57b06483306a3a4d34d88419a088456d_Traceguids
0x18001aa24  call    WPP_SF_d
0x18001aa29  jmp     loc_18001AB31
0x18001aa2e  xor     r9d, r9d; dwFileOffsetLow
0x18001aa31  mov     qword ptr [rsp+168h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x18001aa3a  xor     r8d, r8d; dwFileOffsetHigh
0x18001aa3d  mov     rcx, rbx; hFileMappingObject
0x18001aa40  lea     edx, [r9+2]; dwDesiredAccess
0x18001aa44  call    cs:__imp_MapViewOfFile
0x18001aa4a  test    rax, rax
0x18001aa4d  jnz     short loc_18001AA8A
0x18001aa4f  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18001aa54  mov     rcx, rbx; hObject
0x18001aa57  mov     edi, eax
0x18001aa59  call    cs:__imp_CloseHandle
0x18001aa5f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aa66  lea     rbx, WPP_GLOBAL_Control
0x18001aa6d  cmp     rcx, rbx
0x18001aa70  jz      loc_18001AB38
0x18001aa76  test    byte ptr [rcx+1Ch], 4
0x18001aa7a  jz      loc_18001AB38
0x18001aa80  mov     edx, 1Eh
0x18001aa85  mov     r9d, edi
0x18001aa88  jmp     short loc_18001AA19
0x18001aa8a  mov     rcx, rax; lpBaseAddress
0x18001aa8d  call    cs:__imp_UnmapViewOfFile
0x18001aa93  xor     edx, edx; Val
0x18001aa95  lea     rcx, [rsp+168h+String]; void *
0x18001aa9a  mov     r8d, 0FFh; Size
0x18001aaa0  call    memset_0
0x18001aaa5  call    cs:__imp_GetCurrentProcessId
0x18001aaab  mov     [rsp+168h+var_138], rbx
0x18001aab0  lea     r8, Format; "%u:%u:%u:%p"
0x18001aab7  mov     dword ptr [rsp+168h+lpName], edi
0x18001aabb  lea     rcx, [rsp+168h+String]; char *
0x18001aac0  mov     r9d, 10h
0x18001aac6  mov     [rsp+168h+dwMaximumSizeLow], eax
0x18001aaca  mov     edx, 0FFh; unsigned __int64
0x18001aacf  call    ?sprintf_sfn@@YAXPEAD_KPEBDZZ; sprintf_sfn(char *,unsigned __int64,char const *,...)
0x18001aad4  lea     rcx, [rsp+168h+String]; lpString
0x18001aad9  call    cs:__imp_GlobalAddAtomA
0x18001aadf  xor     ecx, ecx
0x18001aae1  mov     [r14], ax
0x18001aae5  cmp     cx, ax
0x18001aae8  jnz     short loc_18001AB3E
0x18001aaea  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18001aaef  mov     rcx, rbx; hObject
0x18001aaf2  mov     edi, eax
0x18001aaf4  call    cs:__imp_CloseHandle
0x18001aafa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ab01  lea     rbx, WPP_GLOBAL_Control
0x18001ab08  cmp     rcx, rbx
0x18001ab0b  jz      short loc_18001AB38
0x18001ab0d  test    byte ptr [rcx+1Ch], 4
0x18001ab11  jz      short loc_18001AB38
0x18001ab13  mov     rcx, [rcx+10h]
0x18001ab17  lea     r9, [rsp+168h+String]
0x18001ab1c  mov     edx, 1Fh
0x18001ab21  mov     [rsp+168h+dwMaximumSizeLow], edi
0x18001ab25  lea     r8, WPP_57b06483306a3a4d34d88419a088456d_Traceguids
0x18001ab2c  call    WPP_SF_sD
0x18001ab31  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ab38  test    edi, edi
0x18001ab3a  js      short loc_18001AB93
0x18001ab3c  jmp     short loc_18001AB7B
0x18001ab3e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ab45  lea     rbx, WPP_GLOBAL_Control
0x18001ab4c  xor     edi, edi
0x18001ab4e  cmp     rcx, rbx
0x18001ab51  jz      short loc_18001AB7B
0x18001ab53  test    byte ptr [rcx+1Ch], 8
0x18001ab57  jz      short loc_18001AB7B
0x18001ab59  mov     rcx, [rcx+10h]
0x18001ab5d  movzx   r9d, ax
0x18001ab61  lea     rax, [rsp+168h+String]
0x18001ab66  mov     dword ptr [rsp+168h+lpName], edi
0x18001ab6a  mov     qword ptr [rsp+168h+dwMaximumSizeLow], rax
0x18001ab6f  call    WPP_SF_DsD
0x18001ab74  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ab7b  test    ebp, ebp
0x18001ab7d  jz      short loc_18001AB93
0x18001ab7f  movzx   ecx, word ptr [r14]; unsigned __int16
0x18001ab83  mov     edx, ebp; unsigned int
0x18001ab85  call    ?HrResizeMarshalID@@YAJGK@Z; HrResizeMarshalID(ushort,ulong)
0x18001ab8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ab91  mov     edi, eax
0x18001ab93  cmp     rcx, rbx
0x18001ab96  jz      short loc_18001ABB6
0x18001ab98  test    byte ptr [rcx+1Ch], 10h
0x18001ab9c  jz      short loc_18001ABB6
0x18001ab9e  mov     rcx, [rcx+10h]
0x18001aba2  lea     r8, WPP_57b06483306a3a4d34d88419a088456d_Traceguids
0x18001aba9  mov     edx, 21h ; '!'
0x18001abae  mov     r9d, edi
0x18001abb1  call    WPP_SF_d
0x18001abb6  mov     eax, edi
0x18001abb8  mov     rcx, [rsp+168h+var_28]
0x18001abc0  xor     rcx, rsp; StackCookie
0x18001abc3  call    __security_check_cookie
0x18001abc8  mov     rbx, [rsp+168h+arg_18]
0x18001abd0  add     rsp, 150h
0x18001abd7  pop     r14
0x18001abd9  pop     rdi
0x18001abda  pop     rbp
0x18001abdb  retn
```
