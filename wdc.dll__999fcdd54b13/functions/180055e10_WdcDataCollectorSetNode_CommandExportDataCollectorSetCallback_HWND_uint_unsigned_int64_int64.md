# WdcDataCollectorSetNode::CommandExportDataCollectorSetCallback(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180055e10`
- end: `0x180056065`
- name: `?CommandExportDataCollectorSetCallback@WdcDataCollectorSetNode@@CA_KPEAUHWND__@@I_K_J@Z`
- size: `597`
- prototype: `__int64 __fastcall(HWND hWnd, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800044ac`
- `0x1800071e0`
- `0x180008ab0`
- `0x18000b7d0`
- `0x18000b854`
- `0x18003b0ac`
- `0x180055e10`
- `0x18005934c`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180055e8a`
- `KERNEL32!CreateFileW` at `0x180055e8a`
- `KERNEL32!CloseHandle` at `0x180056048`
- `KERNEL32!CloseHandle` at `0x180056048`
- `KERNEL32!GetLastError` at `0x180055e99`
- `KERNEL32!GetLastError` at `0x180055e99`
- `USER32!SetWindowLongPtrW` at `0x180056019`
- `USER32!SetWindowLongPtrW` at `0x180056019`

## string_xrefs

- `0x180055ef4`: `WdcDataCollectorSetNode::CommandExportDataCollectorSetCallback`
- `0x180055f33`: `WdcDataCollectorSetNode::CommandExportDataCollectorSetCallback`
- `0x180055f73`: `WdcDataCollectorSetNode::CommandExportDataCollectorSetCallback`

## pseudocode

```c
__int64 __fastcall WdcDataCollectorSetNode::CommandExportDataCollectorSetCallback(
        HWND hWnd,
        int a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v7; // r15
  unsigned __int16 v8; // bx
  char *FileW; // r14
  signed int LastError; // eax
  const char *v11; // rdx
  int v12; // r8d
  const char *v13; // rdx
  unsigned __int16 *v14; // rbx
  int v15; // r8d
  WCHAR *v16; // rdi
  const char *v17; // rdx
  int v18; // r8d
  int String; // eax
  const char *v20; // rdx
  int v21; // r8d
  __int64 dwCreationDisposition; // [rsp+20h] [rbp-A9h]
  int v24; // [rsp+40h] [rbp-89h] BYREF
  HWND v25; // [rsp+44h] [rbp-85h]
  HINSTANCE v26; // [rsp+4Ch] [rbp-7Dh]
  int v27; // [rsp+54h] [rbp-75h]
  int v28; // [rsp+58h] [rbp-71h]
  __int64 v29; // [rsp+5Ch] [rbp-6Dh]
  __int64 v30; // [rsp+64h] [rbp-65h]
  unsigned __int16 *v31; // [rsp+6Ch] [rbp-5Dh]
  int v32; // [rsp+7Ch] [rbp-4Dh]
  __int64 *v33; // [rsp+80h] [rbp-49h]
  char *v34; // [rsp+138h] [rbp+6Fh] BYREF

  v7 = 0;
  memset_0(&v24, 0, 0xA0u);
  LODWORD(v34) = 0;
  if ( a2 == 78 && *(_DWORD *)(a4 + 16) == -606 )
  {
    v8 = 0;
    FileW = (char *)CreateFileW(*(LPCWSTR *)(*(_QWORD *)(a4 + 24) + 48LL), 0x80000000, 3u, 0, 3u, 0x80u, 0);
    if ( FileW == (char *)-1LL )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        v8 = LastError;
        if ( LastError > 0 )
          v8 = LastError;
      }
    }
    if ( (unsigned int)v8 - 2 > 1 )
    {
      memset_0(&v24, 0, 0xA0u);
      v14 = (unsigned __int16 *)WdcAlloc(0x800u, v11, v12);
      if ( v14 )
      {
        *v14 = 0;
        v16 = (WCHAR *)WdcAlloc(0x800u, v13, v15);
        if ( v16 )
        {
          *v16 = 0;
          String = WdcLoadString(0x51u, v16, 0x400u);
          if ( String < 0 )
            goto LABEL_13;
          String = StringCchPrintfW(v14, 0x400u, v16, *(_QWORD *)(*(_QWORD *)(a4 + 24) + 48LL));
          if ( String < 0 )
            goto LABEL_13;
          v26 = g_hInstance;
          v24 = 160;
          v33 = qword_1800B1610;
          v27 = 16;
          v25 = hWnd;
          v29 = 80;
          v28 = 8;
          v30 = 0xFFFF;
          v31 = v14;
          v32 = 2;
          String = IsolationAwareTaskDialogIndirect(&v24, &v34);
          if ( String < 0 )
          {
LABEL_13:
            LODWORD(dwCreationDisposition) = String;
            WdcDebugMessage(
              "base\\diagnosis\\pdui\\perfmon\\mmc\\datacollectorsetnode.cpp",
              "WdcDataCollectorSetNode::CommandExportDataCollectorSetCallback",
              0,
              L"FAILURE: 0x%08x",
              dwCreationDisposition);
          }
          else
          {
            v20 = (const char *)(unsigned int)v34;
            if ( (_DWORD)v34 == 2 )
            {
              v7 = 2;
              SetWindowLongPtrW(hWnd, 0, 2);
            }
            else
            {
              **(_DWORD **)(*(_QWORD *)(a4 + 24) + 112LL) = (_DWORD)v34;
            }
          }
          WdcFree(v16, v20, v21);
        }
        else
        {
          LODWORD(dwCreationDisposition) = -2147024882;
          WdcDebugMessage(
            "base\\diagnosis\\pdui\\perfmon\\mmc\\datacollectorsetnode.cpp",
            "WdcDataCollectorSetNode::CommandExportDataCollectorSetCallback",
            0,
            L"FAILURE: 0x%08x",
            dwCreationDisposition);
        }
        WdcFree(v14, v17, v18);
      }
      else
      {
        LODWORD(dwCreationDisposition) = -2147024882;
        WdcDebugMessage(
          "base\\diagnosis\\pdui\\perfmon\\mmc\\datacollectorsetnode.cpp",
          "WdcDataCollectorSetNode::CommandExportDataCollectorSetCallback",
          0,
          L"FAILURE: 0x%08x",
          dwCreationDisposition);
      }
    }
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(FileW);
  }
  return v7;
}

```

## disassembly

```asm
0x180055e10  push    rbp
0x180055e12  push    rbx
0x180055e13  push    rsi
0x180055e14  push    rdi
0x180055e15  push    r12
0x180055e17  push    r13
0x180055e19  push    r14
0x180055e1b  push    r15
0x180055e1d  lea     rbp, [rsp-1Fh]
0x180055e22  sub     rsp, 0E8h
0x180055e29  mov     ebx, edx
0x180055e2b  mov     r12, rcx
0x180055e2e  mov     edi, 0A0h
0x180055e33  lea     rcx, [rsp+120h+var_E0]; void *
0x180055e38  mov     r8d, edi; Size
0x180055e3b  xor     edx, edx; Val
0x180055e3d  mov     rsi, r9
0x180055e40  xor     r15d, r15d
0x180055e43  call    memset_0
0x180055e48  mov     dword ptr [rbp+57h+arg_8], r15d
0x180055e4c  cmp     ebx, 4Eh ; 'N'
0x180055e4f  jnz     loc_18005604E
0x180055e55  cmp     dword ptr [rsi+10h], 0FFFFFDA2h
0x180055e5c  jnz     loc_18005604E
0x180055e62  mov     rcx, [rsi+18h]
0x180055e66  lea     r8d, [r15+3]; dwShareMode
0x180055e6a  xor     ebx, ebx
0x180055e6c  xor     r9d, r9d; lpSecurityAttributes
0x180055e6f  mov     [rsp+120h+hTemplateFile], rbx; hTemplateFile
0x180055e74  mov     edx, 80000000h; dwDesiredAccess
0x180055e79  mov     [rsp+120h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180055e81  mov     rcx, [rcx+30h]; lpFileName
0x180055e85  mov     dword ptr [rsp+120h+dwCreationDisposition], r8d; dwCreationDisposition
0x180055e8a  call    cs:__imp_CreateFileW
0x180055e90  mov     r14, rax
0x180055e93  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180055e97  jnz     short loc_180055EAA
0x180055e99  call    cs:__imp_GetLastError
0x180055e9f  test    eax, eax
0x180055ea1  jz      short loc_180055EAA
0x180055ea3  mov     ebx, eax
0x180055ea5  jle     short loc_180055EAA
0x180055ea7  movzx   ebx, ax
0x180055eaa  movzx   eax, bx
0x180055ead  mov     r13d, 2
0x180055eb3  sub     eax, r13d
0x180055eb6  cmp     eax, 1
0x180055eb9  jbe     loc_18005603B
0x180055ebf  mov     r8, rdi; Size
0x180055ec2  lea     rcx, [rsp+120h+var_E0]; void *
0x180055ec7  xor     edx, edx; Val
0x180055ec9  call    memset_0
0x180055ece  mov     edi, 800h
0x180055ed3  mov     ecx, edi; dwBytes
0x180055ed5  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x180055eda  mov     rbx, rax
0x180055edd  test    rax, rax
0x180055ee0  jnz     short loc_180055F0C
0x180055ee2  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180055ee9  mov     dword ptr [rsp+120h+dwCreationDisposition], 8007000Eh
0x180055ef1  xor     r8d, r8d; int
0x180055ef4  lea     rdx, aWdcdatacollect_18; "WdcDataCollectorSetNode::CommandExportD"...
0x180055efb  lea     rcx, aBaseDiagnosisP_30; "base\\diagnosis\\pdui\\perfmon\\mmc\\da"...
0x180055f02  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180055f07  jmp     loc_18005603B
0x180055f0c  xor     eax, eax
0x180055f0e  mov     rcx, rdi; dwBytes
0x180055f11  mov     [rbx], ax
0x180055f14  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x180055f19  mov     rdi, rax
0x180055f1c  test    rax, rax
0x180055f1f  jnz     short loc_180055F4B
0x180055f21  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180055f28  mov     dword ptr [rsp+120h+dwCreationDisposition], 8007000Eh
0x180055f30  xor     r8d, r8d; int
0x180055f33  lea     rdx, aWdcdatacollect_18; "WdcDataCollectorSetNode::CommandExportD"...
0x180055f3a  lea     rcx, aBaseDiagnosisP_30; "base\\diagnosis\\pdui\\perfmon\\mmc\\da"...
0x180055f41  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180055f46  jmp     loc_180056033
0x180055f4b  xor     eax, eax
0x180055f4d  mov     r8d, 400h; cchBufferMax
0x180055f53  mov     rdx, rdi; lpBuffer
0x180055f56  mov     [rdi], ax
0x180055f59  lea     ecx, [rax+51h]; uID
0x180055f5c  call    ?WdcLoadString@@YAJKPEAG_K@Z; WdcLoadString(ulong,ushort *,unsigned __int64)
0x180055f61  test    eax, eax
0x180055f63  jns     short loc_180055F8B
0x180055f65  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180055f6c  mov     dword ptr [rsp+120h+dwCreationDisposition], eax
0x180055f70  xor     r8d, r8d; int
0x180055f73  lea     rdx, aWdcdatacollect_18; "WdcDataCollectorSetNode::CommandExportD"...
0x180055f7a  lea     rcx, aBaseDiagnosisP_30; "base\\diagnosis\\pdui\\perfmon\\mmc\\da"...
0x180055f81  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180055f86  jmp     loc_18005602B
0x180055f8b  mov     r9, [rsi+18h]
0x180055f8f  mov     r8, rdi; unsigned __int16 *
0x180055f92  mov     edx, 400h; unsigned __int64
0x180055f97  mov     rcx, rbx; unsigned __int16 *
0x180055f9a  mov     r9, [r9+30h]
0x180055f9e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180055fa3  test    eax, eax
0x180055fa5  js      short loc_180055F65
0x180055fa7  mov     rax, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x180055fae  lea     rdx, [rbp+57h+arg_8]
0x180055fb2  mov     [rbp+57h+var_D4], rax
0x180055fb6  lea     rcx, [rsp+120h+var_E0]
0x180055fbb  lea     rax, qword_1800B1610
0x180055fc2  mov     [rsp+120h+var_E0], 0A0h
0x180055fca  mov     [rbp+57h+var_A0], rax
0x180055fce  mov     [rbp+57h+var_CC], 10h
0x180055fd5  mov     [rsp+120h+var_DC], r12
0x180055fda  mov     [rbp+57h+var_C4], 50h ; 'P'
0x180055fe2  mov     [rbp+57h+var_C8], 8
0x180055fe9  mov     [rbp+57h+var_BC], 0FFFFh
0x180055ff1  mov     [rbp+57h+var_B4], rbx
0x180055ff5  mov     [rbp+57h+var_A4], r13d
0x180055ff9  call    IsolationAwareTaskDialogIndirect
0x180055ffe  test    eax, eax
0x180056000  js      loc_180055F65
0x180056006  mov     edx, dword ptr [rbp+57h+arg_8]; char *
0x180056009  cmp     edx, r13d
0x18005600c  jnz     short loc_180056021
0x18005600e  mov     r8, r13; dwNewLong
0x180056011  xor     edx, edx; nIndex
0x180056013  mov     rcx, r12; hWnd
0x180056016  mov     r15, r13
0x180056019  call    cs:__imp_SetWindowLongPtrW
0x18005601f  jmp     short loc_18005602B
0x180056021  mov     rax, [rsi+18h]
0x180056025  mov     rcx, [rax+70h]
0x180056029  mov     [rcx], edx
0x18005602b  mov     rcx, rdi; void *
0x18005602e  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x180056033  mov     rcx, rbx; void *
0x180056036  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x18005603b  lea     rcx, [r14-1]
0x18005603f  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180056043  ja      short loc_18005604E
0x180056045  mov     rcx, r14; hObject
0x180056048  call    cs:__imp_CloseHandle
0x18005604e  mov     rax, r15
0x180056051  add     rsp, 0E8h
0x180056058  pop     r15
0x18005605a  pop     r14
0x18005605c  pop     r13
0x18005605e  pop     r12
0x180056060  pop     rdi
0x180056061  pop     rsi
0x180056062  pop     rbx
0x180056063  pop     rbp
0x180056064  retn
```
