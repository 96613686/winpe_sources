# CSxWindowsUpdateEnumerator::_CleanupOldHives(ushort const *)

- ea: `0x180004e20`
- end: `0x180005085`
- name: `?_CleanupOldHives@CSxWindowsUpdateEnumerator@@CAJPEBG@Z`
- size: `613`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, installer_update`

## callers

- `0x18000408c`
- `0x1800055a4`

## callees

- `0x180003ce0`
- `0x180004e20`
- `0x18000d348`
- `0x18000d43c`
- `0x18000dd64`
- `0x18000f154`
- `0x180014e30`
- `0x180014f38`
- `0x1800152f0`
- `0x180015760`
- `0x1800157be`
- `0x1800157f0`

## import_xrefs

- `KERNEL32!FindFirstFileW` at `0x180004f54`
- `KERNEL32!FindFirstFileW` at `0x180004f54`
- `KERNEL32!GetLastError` at `0x180004fdb`
- `KERNEL32!GetLastError` at `0x180004fdb`
- `KERNEL32!FindNextFileW` at `0x180004fd1`
- `KERNEL32!FindNextFileW` at `0x180004fd1`
- `KERNEL32!FindClose` at `0x18000502b`
- `KERNEL32!FindClose` at `0x18000502b`

## string_xrefs

- `0x180004e88`: `CSxWindowsUpdateEnumerator::_CleanupOldHives`

## pseudocode

```c
__int64 __fastcall CSxWindowsUpdateEnumerator::_CleanupOldHives(const unsigned __int16 *a1)
{
  LPCWSTR v2; // rdi
  __int64 FirstFileW; // rsi
  const unsigned __int16 *v4; // r8
  const unsigned __int16 *v5; // r9
  __int16 v6; // ax
  unsigned __int16 *v7; // rbx
  __int64 v8; // rax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // r8
  const unsigned __int16 *v13; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v14; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v15; // [rsp+38h] [rbp-C8h]
  LPCWSTR v16; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v17; // [rsp+48h] [rbp-B8h]
  int LastFailureAsHRESULT; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v19; // [rsp+54h] [rbp-ACh]
  __int16 v20; // [rsp+56h] [rbp-AAh]
  LPCWSTR lpFileName[3]; // [rsp+88h] [rbp-78h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+A0h] [rbp-60h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_012e94a410f034635dd5ee797f3d6253_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&LastFailureAsHRESULT,
    "CSxWindowsUpdateEnumerator::_CleanupOldHives",
    208);
  v2 = (LPCWSTR)qword_18001A620;
  lpFileName[1] = 0;
  lpFileName[0] = (LPCWSTR)qword_18001A620;
  v14 = (unsigned __int16 *)qword_18001A620;
  v16 = (LPCWSTR)qword_18001A620;
  FirstFileW = -1;
  v15 = 0;
  v17 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  LastFailureAsHRESULT = CBsString::Append((CBsString *)&v14, a1);
  v6 = 216;
  if ( LastFailureAsHRESULT >= 0 )
  {
    v7 = v14;
    v19 = 216;
    if ( (_DWORD)v15 )
    {
      v8 = (unsigned int)(v15 - 1);
      if ( v14[v8] == 92 && (unsigned int)v8 <= HIDWORD(v15) )
      {
        LODWORD(v15) = v15 - 1;
        v14[(unsigned int)v8] = 0;
      }
    }
    LastFailureAsHRESULT = CBsString::Set((CBsString *)lpFileName, v7, v4, v5, v13);
    v6 = 219;
    if ( LastFailureAsHRESULT >= 0 )
    {
      v19 = 219;
      FirstFileW = (__int64)FindFirstFileW(lpFileName[0], &FindFileData);
      if ( FirstFileW == -1 )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT();
        v20 = 224;
        goto LABEL_24;
      }
      LastFailureAsHRESULT = 0;
      v19 = 224;
      do
      {
        if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
        {
          if ( (_DWORD)v17 )
          {
            LODWORD(v17) = 0;
            *v2 = 0;
          }
          LastFailureAsHRESULT = CBsString::Append((CBsString *)&v16, v7, L"\\", FindFileData.cFileName);
          if ( LastFailureAsHRESULT < 0 )
          {
            v20 = 233;
            goto LABEL_24;
          }
          v2 = v16;
          v19 = 233;
          SxDeleteFile(v16);
        }
      }
      while ( FindNextFileW((HANDLE)FirstFileW, &FindFileData) );
      if ( GetLastError() == 18 )
      {
        LastFailureAsHRESULT = 0;
        v19 = 240;
        goto LABEL_24;
      }
      LastFailureAsHRESULT = GetLastFailureAsHRESULT();
      v6 = 240;
    }
  }
  v20 = v6;
LABEL_24:
  FindClose((HANDLE)FirstFileW);
  v9 = LastFailureAsHRESULT;
  CBsString::_Release((CBsString *)&v16);
  CBsString::_Release((CBsString *)&v14);
  CBsString::_Release((CBsString *)lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, v10, v11);
  return v9;
}

```

## disassembly

```asm
0x180004e20  mov     [rsp-8+arg_8], rbx
0x180004e25  mov     [rsp-8+arg_10], rsi
0x180004e2a  push    rbp
0x180004e2b  push    rdi
0x180004e2c  push    r15
0x180004e2e  lea     rbp, [rsp-200h]
0x180004e36  sub     rsp, 300h
0x180004e3d  mov     rax, cs:__security_cookie
0x180004e44  xor     rax, rsp
0x180004e47  mov     [rbp+210h+var_20], rax
0x180004e4e  mov     rbx, rcx
0x180004e51  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e58  lea     rax, WPP_GLOBAL_Control
0x180004e5f  cmp     rcx, rax
0x180004e62  jz      short loc_180004E82
0x180004e64  test    dword ptr [rcx+1Ch], 20000000h
0x180004e6b  jz      short loc_180004E82
0x180004e6d  mov     rcx, [rcx+10h]
0x180004e71  lea     r8, WPP_012e94a410f034635dd5ee797f3d6253_Traceguids
0x180004e78  mov     edx, 0Bh
0x180004e7d  call    WPP_SF_
0x180004e82  mov     r8d, 0D0h; unsigned __int16
0x180004e88  lea     rdx, aCsxwindowsupda; "CSxWindowsUpdateEnumerator::_CleanupOld"...
0x180004e8f  lea     rcx, [rsp+310h+var_2C0]; this
0x180004e94  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180004e99  lea     rdi, qword_18001A620
0x180004ea0  mov     [rbp+210h+var_280], 0
0x180004ea8  xor     edx, edx; Val
0x180004eaa  mov     [rbp+210h+lpFileName], rdi
0x180004eae  mov     r8d, 250h; Size
0x180004eb4  mov     [rsp+310h+var_2E0], rdi
0x180004eb9  lea     rcx, [rbp+210h+FindFileData]; void *
0x180004ebd  mov     [rsp+310h+var_2D0], rdi
0x180004ec2  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180004ec6  mov     [rsp+310h+var_2D8], 0
0x180004ecf  mov     [rsp+310h+var_2C8], 0
0x180004ed8  call    memset_0
0x180004edd  mov     rdx, rbx; unsigned __int16 *
0x180004ee0  lea     rcx, [rsp+310h+var_2E0]; this
0x180004ee5  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x180004eea  mov     [rsp+310h+var_2C0], eax
0x180004eee  test    eax, eax
0x180004ef0  mov     eax, 0D8h
0x180004ef5  jns     short loc_180004F01
0x180004ef7  mov     [rsp+310h+var_2BA], ax
0x180004efc  jmp     loc_180005028
0x180004f01  mov     rbx, [rsp+310h+var_2E0]
0x180004f06  mov     [rsp+310h+var_2BC], ax
0x180004f0b  mov     eax, dword ptr [rsp+310h+var_2D8]
0x180004f0f  test    eax, eax
0x180004f11  jz      short loc_180004F2E
0x180004f13  dec     eax
0x180004f15  mov     ecx, eax
0x180004f17  cmp     word ptr [rbx+rax*2], 5Ch ; '\'
0x180004f1c  jnz     short loc_180004F2E
0x180004f1e  cmp     eax, dword ptr [rsp+310h+var_2D8+4]
0x180004f22  ja      short loc_180004F2E
0x180004f24  mov     dword ptr [rsp+310h+var_2D8], eax
0x180004f28  xor     eax, eax
0x180004f2a  mov     [rbx+rcx*2], ax
0x180004f2e  mov     rdx, rbx; unsigned __int16 *
0x180004f31  lea     rcx, [rbp+210h+lpFileName]; this
0x180004f35  call    ?Set@CBsString@@QEAAJPEBG000@Z; CBsString::Set(ushort const *,ushort const *,ushort const *,ushort const *)
0x180004f3a  mov     [rsp+310h+var_2C0], eax
0x180004f3e  test    eax, eax
0x180004f40  mov     eax, 0DBh
0x180004f45  js      short loc_180004EF7
0x180004f47  mov     rcx, [rbp+210h+lpFileName]; lpFileName
0x180004f4b  lea     rdx, [rbp+210h+FindFileData]; lpFindFileData
0x180004f4f  mov     [rsp+310h+var_2BC], ax
0x180004f54  call    cs:__imp_FindFirstFileW
0x180004f5a  mov     rsi, rax
0x180004f5d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180004f61  jz      loc_180005015
0x180004f67  mov     ecx, 0E0h
0x180004f6c  mov     [rsp+310h+var_2C0], 0
0x180004f74  mov     [rsp+310h+var_2BC], cx
0x180004f79  lea     r15d, [rcx+9]
0x180004f7d  test    byte ptr [rbp+210h+FindFileData.dwFileAttributes], 10h
0x180004f81  jnz     short loc_180004FCA
0x180004f83  cmp     dword ptr [rsp+310h+var_2C8], 0
0x180004f88  jz      short loc_180004F97
0x180004f8a  xor     eax, eax
0x180004f8c  mov     dword ptr [rsp+310h+var_2C8], 0
0x180004f94  mov     [rdi], ax
0x180004f97  lea     r9, [rbp+210h+FindFileData.cFileName]; unsigned __int16 *
0x180004f9b  mov     rdx, rbx; unsigned __int16 *
0x180004f9e  lea     r8, asc_1800180A8; "\\"
0x180004fa5  lea     rcx, [rsp+310h+var_2D0]; this
0x180004faa  call    ?Append@CBsString@@QEAAJPEBG00@Z; CBsString::Append(ushort const *,ushort const *,ushort const *)
0x180004faf  mov     [rsp+310h+var_2C0], eax
0x180004fb3  test    eax, eax
0x180004fb5  js      short loc_180004FFA
0x180004fb7  mov     rdi, [rsp+310h+var_2D0]
0x180004fbc  mov     rcx, rdi; lpFileName
0x180004fbf  mov     [rsp+310h+var_2BC], r15w
0x180004fc5  call    ?SxDeleteFile@@YAJPEBG@Z; SxDeleteFile(ushort const *)
0x180004fca  lea     rdx, [rbp+210h+FindFileData]; lpFindFileData
0x180004fce  mov     rcx, rsi; hFindFile
0x180004fd1  call    cs:__imp_FindNextFileW
0x180004fd7  test    eax, eax
0x180004fd9  jnz     short loc_180004F7D
0x180004fdb  call    cs:__imp_GetLastError
0x180004fe1  cmp     eax, 12h
0x180004fe4  jnz     short loc_180005002
0x180004fe6  mov     eax, 0F0h
0x180004feb  mov     [rsp+310h+var_2C0], 0
0x180004ff3  mov     [rsp+310h+var_2BC], ax
0x180004ff8  jmp     short loc_180005028
0x180004ffa  mov     [rsp+310h+var_2BA], r15w
0x180005000  jmp     short loc_180005028
0x180005002  call    GetLastFailureAsHRESULT
0x180005007  mov     [rsp+310h+var_2C0], eax
0x18000500b  mov     eax, 0F0h
0x180005010  jmp     loc_180004EF7
0x180005015  call    GetLastFailureAsHRESULT
0x18000501a  mov     ecx, 0E0h
0x18000501f  mov     [rsp+310h+var_2C0], eax
0x180005023  mov     [rsp+310h+var_2BA], cx
0x180005028  mov     rcx, rsi; hFindFile
0x18000502b  call    cs:__imp_FindClose
0x180005031  mov     ebx, [rsp+310h+var_2C0]
0x180005035  lea     rcx, [rsp+310h+var_2D0]; this
0x18000503a  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18000503f  lea     rcx, [rsp+310h+var_2E0]; this
0x180005044  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180005049  lea     rcx, [rbp+210h+lpFileName]; this
0x18000504d  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180005052  lea     rcx, [rsp+310h+var_2C0]; this
0x180005057  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000505c  mov     eax, ebx
0x18000505e  mov     rcx, [rbp+210h+var_20]
0x180005065  xor     rcx, rsp; StackCookie
0x180005068  call    __security_check_cookie
0x18000506d  lea     r11, [rsp+310h+var_10]
0x180005075  mov     rbx, [r11+28h]
0x180005079  mov     rsi, [r11+30h]
0x18000507d  mov     rsp, r11
0x180005080  pop     r15
0x180005082  pop     rdi
0x180005083  pop     rbp
0x180005084  retn
```
