# AsrVhd::GetDeviceDependencyInformation(ushort const *,uchar,_STORAGE_DEPENDENCY_INFO_VERSION,_STORAGE_DEPENDENCY_INFO * *)

- ea: `0x140021f14`
- end: `0x140022283`
- name: `?GetDeviceDependencyInformation@AsrVhd@@SAHPEBGEW4_STORAGE_DEPENDENCY_INFO_VERSION@@PEAPEAU_STORAGE_DEPENDENCY_INFO@@@Z`
- size: `879`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned __int8, enum _STORAGE_DEPENDENCY_INFO_VERSION, struct _STORAGE_DEPENDENCY_INFO **)`
- caller_count: `5`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1400235e0`
- `0x1400253dc`
- `0x14005a294`
- `0x14005c798`
- `0x1400d299c`

## callees

- `0x140021ca0`
- `0x140021f14`
- `0x140025abc`
- `0x14003b0c0`
- `0x1400d257c`
- `0x1400d26c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002226a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002226a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002219e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400221c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002219e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400221c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140022256`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140022256`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140022008`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140022008`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002207a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140022242`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002207a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140022242`
- `VirtDisk!GetStorageDependencyInformation` at `0x140022041`
- `VirtDisk!GetStorageDependencyInformation` at `0x140022041`

## string_xrefs

- `0x140022223`: `wszDevicepath`

## pseudocode

```c
__int64 __fastcall AsrVhd::GetDeviceDependencyInformation(
        LPCWSTR lpFileName,
        char a2,
        STORAGE_DEPENDENCY_INFO_VERSION a3,
        struct _STORAGE_DEPENDENCY_INFO **a4)
{
  struct _DRIVE_LAYOUT_INFORMATION_EX *v8; // rcx
  unsigned int v9; // ebx
  DWORD LastError; // edi
  __int64 FileW; // r12
  struct _STORAGE_DEPENDENCY_INFO *v12; // rsi
  int v13; // r9d
  int v14; // edx
  const char *v15; // rax
  unsigned int v16; // ebp
  DWORD StorageDependencyInformation; // eax
  struct _STORAGE_DEPENDENCY_INFO *v18; // rax
  DWORD v19; // eax
  ULONG SizeUsed; // [rsp+90h] [rbp+8h] BYREF

  v8 = WPP_GLOBAL_Control;
  v9 = 1;
  if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x100000000LL) != 0 )
  {
    WPP_SF_S(
      *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
      10,
      WPP_1ff3ecedd42930a16d896984b72cfff5_Traceguids,
      L"AsrVhd::GetDeviceDependencyInformation");
    v8 = WPP_GLOBAL_Control;
  }
  LastError = 0;
  FileW = -1;
  SizeUsed = 0;
  v12 = 0;
  if ( lpFileName )
  {
    if ( (unsigned int)(a3 - 1) <= 1 )
    {
      if ( a4 )
      {
        *a4 = 0;
        SizeUsed = 136;
        v12 = (struct _STORAGE_DEPENDENCY_INFO *)ASR_ALLOC(0x88u);
        v12->Version = a3;
        FileW = (__int64)CreateFileW(lpFileName, 0x80000000, 3u, 0, 3u, 0x80u, 0);
        if ( FileW == -1 )
        {
          v9 = 0;
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
          {
            v19 = GetLastError();
            WPP_SF_Ds(
              *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
              32,
              (unsigned int)WPP_a86e46cab1e6364cac808a299cf5a63f_Traceguids,
              v19,
              "hDevice != INVALID_HANDLE_VALUE");
          }
        }
        else
        {
          v16 = a2 != 0 ? 0xFFFFFFFE : 0;
          while ( 1 )
          {
            StorageDependencyInformation = GetStorageDependencyInformation(
                                             (HANDLE)FileW,
                                             (GET_STORAGE_DEPENDENCY_FLAG)(v16 + 3),
                                             SizeUsed,
                                             v12,
                                             &SizeUsed);
            if ( !StorageDependencyInformation )
            {
              if ( v12->NumberEntries )
              {
                *a4 = v12;
                v12 = 0;
              }
              else if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
                     && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x200000000LL) != 0 )
              {
                WPP_SF_S(
                  *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
                  36,
                  WPP_a86e46cab1e6364cac808a299cf5a63f_Traceguids,
                  lpFileName);
              }
              goto LABEL_44;
            }
            if ( StorageDependencyInformation == 1
              || StorageDependencyInformation == 50
              || StorageDependencyInformation == -1069940715 )
            {
              if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
                && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x200000000LL) != 0 )
              {
                WPP_SF_SD(
                  *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
                  33,
                  (unsigned int)WPP_a86e46cab1e6364cac808a299cf5a63f_Traceguids,
                  (_DWORD)lpFileName,
                  StorageDependencyInformation);
              }
              goto LABEL_44;
            }
            if ( StorageDependencyInformation != 122 && StorageDependencyInformation != 234 )
            {
              v9 = 0;
              LastError = StorageDependencyInformation;
              if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
                && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
              {
                WPP_SF_Ds(
                  *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
                  34,
                  (unsigned int)WPP_a86e46cab1e6364cac808a299cf5a63f_Traceguids,
                  StorageDependencyInformation,
                  "dwError");
              }
              goto LABEL_44;
            }
            CoTaskMemFree(v12);
            v18 = (struct _STORAGE_DEPENDENCY_INFO *)ASR_ALLOC(SizeUsed);
            v12 = v18;
            if ( !v18 )
              break;
            v18->Version = a3;
          }
          v9 = 0;
          LastError = 14;
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
          {
            v14 = 35;
            v13 = 14;
            v15 = "pVhdInfo";
            goto LABEL_43;
          }
        }
      }
      else
      {
        v13 = 87;
        v9 = 0;
        LastError = 87;
        if ( v8 != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
          && (v8->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
        {
          v14 = 31;
          v15 = "ppDependencyInfo";
          goto LABEL_43;
        }
      }
    }
    else
    {
      v13 = 87;
      v9 = 0;
      LastError = 87;
      if ( v8 != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        && (v8->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
      {
        v14 = 30;
        v15 = "sdiVersion == STORAGE_DEPENDENCY_INFO_VERSION_1 || sdiVersion == STORAGE_DEPENDENCY_INFO_VERSION_2";
LABEL_43:
        WPP_SF_Ds(
          *(_QWORD *)v8->Gpt.DiskId.Data4,
          v14,
          (unsigned int)WPP_a86e46cab1e6364cac808a299cf5a63f_Traceguids,
          v13,
          v15);
      }
    }
  }
  else
  {
    v13 = 87;
    v9 = 0;
    LastError = 87;
    if ( v8 != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (v8->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v14 = 29;
      v15 = "wszDevicepath";
      goto LABEL_43;
    }
  }
LABEL_44:
  CoTaskMemFree(v12);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  TraceFunctionExit(L"AsrVhd::GetDeviceDependencyInformation");
  SetLastError(LastError);
  return v9;
}

```

## disassembly

```asm
0x140021f14  push    rbx
0x140021f16  push    rbp
0x140021f17  push    rsi
0x140021f18  push    rdi
0x140021f19  push    r12
0x140021f1b  push    r13
0x140021f1d  push    r14
0x140021f1f  push    r15
0x140021f21  sub     rsp, 48h
0x140021f25  mov     r15, r9
0x140021f28  mov     r13d, r8d
0x140021f2b  mov     bpl, dl
0x140021f2e  mov     r14, rcx
0x140021f31  mov     rcx, cs:WPP_GLOBAL_Control
0x140021f38  lea     rdx, WPP_GLOBAL_Control
0x140021f3f  mov     ebx, 1
0x140021f44  cmp     rcx, rdx
0x140021f47  jz      short loc_140021F76
0x140021f49  test    [rcx+1Ch], bl
0x140021f4c  jz      short loc_140021F76
0x140021f4e  mov     rcx, [rcx+10h]
0x140021f52  lea     edx, [rbx+9]
0x140021f55  lea     r9, aAsrvhdGetdevic_0; "AsrVhd::GetDeviceDependencyInformation"
0x140021f5c  lea     r8, WPP_1ff3ecedd42930a16d896984b72cfff5_Traceguids
0x140021f63  call    WPP_SF_S
0x140021f68  mov     rcx, cs:WPP_GLOBAL_Control
0x140021f6f  lea     rdx, WPP_GLOBAL_Control
0x140021f76  xor     edi, edi
0x140021f78  or      r12, 0FFFFFFFFFFFFFFFFh
0x140021f7c  mov     [rsp+88h+SizeUsed], edi
0x140021f83  mov     esi, edi
0x140021f85  test    r14, r14
0x140021f88  jz      loc_140022209
0x140021f8e  lea     eax, [r13-1]
0x140021f92  cmp     eax, ebx
0x140021f94  jbe     short loc_140021FC1
0x140021f96  lea     r9d, [rdi+57h]
0x140021f9a  mov     ebx, edi
0x140021f9c  mov     edi, r9d
0x140021f9f  cmp     rcx, rdx
0x140021fa2  jz      loc_14002223F
0x140021fa8  test    byte ptr [rcx+1Ch], 8
0x140021fac  jz      loc_14002223F
0x140021fb2  lea     edx, [rsi+1Eh]
0x140021fb5  lea     rax, aSdiversionStor; "sdiVersion == STORAGE_DEPENDENCY_INFO_V"...
0x140021fbc  jmp     loc_14002222A
0x140021fc1  test    r15, r15
0x140021fc4  jz      loc_1400221E6
0x140021fca  mov     ecx, 88h; Size
0x140021fcf  mov     [r15], rdi
0x140021fd2  mov     [rsp+88h+SizeUsed], ecx
0x140021fd9  call    ?ASR_ALLOC@@YAPEAXK@Z; ASR_ALLOC(ulong)
0x140021fde  mov     rsi, rax
0x140021fe1  mov     [rsp+88h+hTemplateFile], rdi; hTemplateFile
0x140021fe6  mov     [rsp+88h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x140021fee  xor     r9d, r9d; lpSecurityAttributes
0x140021ff1  mov     edx, 80000000h; dwDesiredAccess
0x140021ff6  mov     rcx, r14; lpFileName
0x140021ff9  mov     [rax], r13d
0x140021ffc  mov     eax, 3
0x140022001  mov     r8d, eax; dwShareMode
0x140022004  mov     [rsp+88h+dwCreationDisposition], eax; dwCreationDisposition
0x140022008  call    cs:__imp_CreateFileW
0x14002200e  mov     r12, rax
0x140022011  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140022015  jz      loc_14002219C
0x14002201b  neg     bpl
0x14002201e  sbb     ebp, ebp
0x140022020  and     ebp, 0FFFFFFFEh
0x140022023  mov     r8d, [rsp+88h+SizeUsed]; StorageDependencyInfoSize
0x14002202b  lea     rax, [rsp+88h+SizeUsed]
0x140022033  mov     r9, rsi; StorageDependencyInfo
0x140022036  mov     qword ptr [rsp+88h+dwCreationDisposition], rax; SizeUsed
0x14002203b  lea     edx, [rbp+3]; Flags
0x14002203e  mov     rcx, r12; ObjectHandle
0x140022041  call    cs:__imp_GetStorageDependencyInformation
0x140022047  test    eax, eax
0x140022049  jz      loc_14002214F
0x14002204f  cmp     eax, ebx
0x140022051  jz      loc_14002210D
0x140022057  cmp     eax, 32h ; '2'
0x14002205a  jz      loc_14002210D
0x140022060  cmp     eax, 0C03A0015h
0x140022065  jz      loc_14002210D
0x14002206b  cmp     eax, 7Ah ; 'z'
0x14002206e  jz      short loc_140022077
0x140022070  cmp     eax, 0EAh
0x140022075  jnz     short loc_140022099
0x140022077  mov     rcx, rsi; pv
0x14002207a  call    cs:__imp_CoTaskMemFree
0x140022080  mov     ecx, [rsp+88h+SizeUsed]; Size
0x140022087  call    ?ASR_ALLOC@@YAPEAXK@Z; ASR_ALLOC(ulong)
0x14002208c  mov     rsi, rax
0x14002208f  test    rax, rax
0x140022092  jz      short loc_1400220D5
0x140022094  mov     [rax], r13d
0x140022097  jmp     short loc_140022023
0x140022099  xor     ebx, ebx
0x14002209b  mov     edi, eax
0x14002209d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400220a4  lea     rdx, WPP_GLOBAL_Control
0x1400220ab  cmp     rcx, rdx
0x1400220ae  jz      loc_14002223F
0x1400220b4  test    byte ptr [rcx+1Ch], 8
0x1400220b8  jz      loc_14002223F
0x1400220be  lea     r8, aDwerror; "dwError"
0x1400220c5  mov     r9d, eax
0x1400220c8  mov     qword ptr [rsp+88h+dwCreationDisposition], r8
0x1400220cd  lea     edx, [rbx+22h]
0x1400220d0  jmp     loc_14002222F
0x1400220d5  xor     ebx, ebx
0x1400220d7  lea     edi, [rbx+0Eh]
0x1400220da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400220e1  lea     rdx, WPP_GLOBAL_Control
0x1400220e8  cmp     rcx, rdx
0x1400220eb  jz      loc_14002223F
0x1400220f1  test    byte ptr [rcx+1Ch], 8
0x1400220f5  jz      loc_14002223F
0x1400220fb  lea     edx, [rbx+23h]
0x1400220fe  mov     r9d, edi
0x140022101  lea     rax, aPvhdinfo; "pVhdInfo"
0x140022108  jmp     loc_14002222A
0x14002210d  mov     rcx, cs:WPP_GLOBAL_Control
0x140022114  lea     rdx, WPP_GLOBAL_Control
0x14002211b  cmp     rcx, rdx
0x14002211e  jz      loc_14002223F
0x140022124  test    byte ptr [rcx+1Ch], 2
0x140022128  jz      loc_14002223F
0x14002212e  mov     rcx, [rcx+10h]
0x140022132  lea     r8, WPP_a86e46cab1e6364cac808a299cf5a63f_Traceguids
0x140022139  mov     edx, 21h ; '!'
0x14002213e  mov     [rsp+88h+dwCreationDisposition], eax
0x140022142  mov     r9, r14
0x140022145  call    WPP_SF_SD
0x14002214a  jmp     loc_14002223F
0x14002214f  cmp     [rsi+4], edi
0x140022152  jnz     short loc_140022192
0x140022154  mov     rcx, cs:WPP_GLOBAL_Control
0x14002215b  lea     rdx, WPP_GLOBAL_Control
0x140022162  cmp     rcx, rdx
0x140022165  jz      loc_14002223F
0x14002216b  test    byte ptr [rcx+1Ch], 2
0x14002216f  jz      loc_14002223F
0x140022175  mov     rcx, [rcx+10h]
0x140022179  lea     r8, WPP_a86e46cab1e6364cac808a299cf5a63f_Traceguids
0x140022180  mov     edx, 24h ; '$'
0x140022185  mov     r9, r14
0x140022188  call    WPP_SF_S
0x14002218d  jmp     loc_14002223F
0x140022192  mov     [r15], rsi
0x140022195  xor     esi, esi
0x140022197  jmp     loc_14002223F
0x14002219c  mov     ebx, edi
0x14002219e  call    cs:__imp_GetLastError
0x1400221a4  mov     edi, eax
0x1400221a6  mov     rax, cs:WPP_GLOBAL_Control
0x1400221ad  lea     rdx, WPP_GLOBAL_Control
0x1400221b4  cmp     rax, rdx
0x1400221b7  jz      loc_14002223F
0x1400221bd  test    byte ptr [rax+1Ch], 8
0x1400221c1  jz      short loc_14002223F
0x1400221c3  call    cs:__imp_GetLastError
0x1400221c9  lea     rcx, aHdeviceInvalid; "hDevice != INVALID_HANDLE_VALUE"
0x1400221d0  mov     edx, 20h ; ' '
0x1400221d5  mov     qword ptr [rsp+88h+dwCreationDisposition], rcx
0x1400221da  mov     r9d, eax
0x1400221dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400221e4  jmp     short loc_14002222F
0x1400221e6  mov     r9d, 57h ; 'W'
0x1400221ec  mov     ebx, edi
0x1400221ee  mov     edi, r9d
0x1400221f1  cmp     rcx, rdx
0x1400221f4  jz      short loc_14002223F
0x1400221f6  test    byte ptr [rcx+1Ch], 8
0x1400221fa  jz      short loc_14002223F
0x1400221fc  lea     edx, [r9-38h]
0x140022200  lea     rax, aPpdependencyin; "ppDependencyInfo"
0x140022207  jmp     short loc_14002222A
0x140022209  mov     r9d, 57h ; 'W'
0x14002220f  mov     ebx, edi
0x140022211  mov     edi, r9d
0x140022214  cmp     rcx, rdx
0x140022217  jz      short loc_14002223F
0x140022219  test    byte ptr [rcx+1Ch], 8
0x14002221d  jz      short loc_14002223F
0x14002221f  lea     edx, [r9-3Ah]
0x140022223  lea     rax, aWszdevicepath; "wszDevicepath"
0x14002222a  mov     qword ptr [rsp+88h+dwCreationDisposition], rax
0x14002222f  mov     rcx, [rcx+10h]
0x140022233  lea     r8, WPP_a86e46cab1e6364cac808a299cf5a63f_Traceguids
0x14002223a  call    WPP_SF_Ds
0x14002223f  mov     rcx, rsi; pv
0x140022242  call    cs:__imp_CoTaskMemFree
0x140022248  lea     rdx, [r12-1]
0x14002224d  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x140022251  ja      short loc_14002225C
0x140022253  mov     rcx, r12; hObject
0x140022256  call    cs:__imp_CloseHandle
0x14002225c  lea     rcx, aAsrvhdGetdevic_0; "AsrVhd::GetDeviceDependencyInformation"
0x140022263  call    ?TraceFunctionExit@@YAXPEAG@Z; TraceFunctionExit(ushort *)
0x140022268  mov     ecx, edi; dwErrCode
0x14002226a  call    cs:__imp_SetLastError
0x140022270  mov     eax, ebx
0x140022272  add     rsp, 48h
0x140022276  pop     r15
0x140022278  pop     r14
0x14002227a  pop     r13
0x14002227c  pop     r12
0x14002227e  pop     rdi
0x14002227f  pop     rsi
0x140022280  pop     rbp
0x140022281  pop     rbx
0x140022282  retn
```
