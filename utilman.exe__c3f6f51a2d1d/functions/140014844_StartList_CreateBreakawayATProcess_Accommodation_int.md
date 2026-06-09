# StartList::CreateBreakawayATProcess(Accommodation *,int)

- ea: `0x140014844`
- end: `0x140014c1d`
- name: `?CreateBreakawayATProcess@StartList@@AEAAJPEAVAccommodation@@H@Z`
- size: `985`
- prototype: `int(StartList *__hidden this, struct Accommodation *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400172b0`

## callees

- `0x140002fa0`
- `0x1400088cc`
- `0x140013fdc`
- `0x140014844`
- `0x1400153e4`
- `0x140017a8c`
- `0x140018010`
- `0x1400189dc`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140014bd9`
- `KERNEL32!HeapFree` at `0x140014bd9`
- `KERNEL32!DeleteProcThreadAttributeList` at `0x140014bb4`
- `KERNEL32!DeleteProcThreadAttributeList` at `0x140014bb4`
- `KERNEL32!CreateProcessW` at `0x140014b72`
- `KERNEL32!CreateProcessW` at `0x140014b72`
- `KERNEL32!UpdateProcThreadAttribute` at `0x140014b22`
- `KERNEL32!UpdateProcThreadAttribute` at `0x140014b22`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x140014aa8`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x140014aed`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x140014aa8`
- `KERNEL32!InitializeProcThreadAttributeList` at `0x140014aed`
- `KERNEL32!GetLastError` at `0x1400148e9`
- `KERNEL32!GetLastError` at `0x1400148e9`
- `KERNEL32!CloseHandle` at `0x140014b89`
- `KERNEL32!CloseHandle` at `0x140014b99`
- `KERNEL32!CloseHandle` at `0x140014b89`
- `KERNEL32!CloseHandle` at `0x140014b99`
- `KERNEL32!HeapAlloc` at `0x140014acc`
- `KERNEL32!HeapAlloc` at `0x140014acc`
- `KERNEL32!GetProcessHeap` at `0x140014ab8`
- `KERNEL32!GetProcessHeap` at `0x140014bc5`
- `KERNEL32!GetProcessHeap` at `0x140014ab8`
- `KERNEL32!GetProcessHeap` at `0x140014bc5`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1400148d9`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1400148d9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140014953`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140014a25`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140014a3a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140014be9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140014953`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140014a25`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140014a3a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140014be9`

## string_xrefs

- `0x140014994`: `/launchnarratorupdates`
- `0x14001488b`: `%SystemRoot%\System32\ATBroker.exe`
- `0x1400148d2`: `%SystemRoot%\System32\ATBroker.exe`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StartList::CreateBreakawayATProcess(WCHAR *this, struct Accommodation *a2, int a3)
{
  unsigned __int64 v5; // rdx
  LPWSTR v7; // rbx
  DWORD v8; // eax
  signed int LastError; // eax
  unsigned int v10; // esi
  unsigned __int64 v11; // rax
  LPWSTR v12; // rbx
  char IsEnabled; // al
  char v14; // dl
  const wchar_t *v15; // rcx
  const wchar_t *v16; // rax
  const wchar_t *v17; // rdx
  unsigned __int64 v18; // rdx
  WCHAR *v19; // rbx
  int v20; // eax
  const wchar_t *v21; // rdx
  unsigned __int64 v22; // rdx
  unsigned int v23; // ecx
  int v24; // r15d
  struct _PROC_THREAD_ATTRIBUTE_LIST *v25; // r14
  ULONG_PTR v26; // rsi
  HANDLE ProcessHeap; // rax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v28; // rax
  BOOL updated; // eax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v30; // rcx
  HANDLE v31; // rax
  const wchar_t *lpPreviousValue; // [rsp+30h] [rbp-91h]
  const wchar_t *lpPreviousValuea; // [rsp+30h] [rbp-91h]
  ULONG_PTR Size; // [rsp+58h] [rbp-69h] BYREF
  void *Value; // [rsp+60h] [rbp-61h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+68h] [rbp-59h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+88h] [rbp-39h] BYREF
  struct _PROC_THREAD_ATTRIBUTE_LIST *v38; // [rsp+F0h] [rbp+2Fh]
  LPWSTR lpDst; // [rsp+128h] [rbp+67h] BYREF
  void *Block; // [rsp+140h] [rbp+7Fh] BYREF

  lpDst = this;
  if ( (unsigned int)Accommodation::IsRunning(a2) )
    return 0;
  lpDst = 0;
  if ( (int)StringCchLengthW(StartList::_atBrokerExe, v5, (unsigned __int64 *)&lpDst) >= 0 )
  {
    v7 = lpDst + 130;
    if ( lpDst + 130 >= lpDst )
    {
      lpDst = 0;
      if ( (unsigned __int8)ATL::CHeapPtr<unsigned short,ATL::CCRTAllocator>::Allocate(&lpDst, v7) )
      {
        v8 = ExpandEnvironmentStringsW(StartList::_atBrokerExe, lpDst, (DWORD)v7);
        if ( !v8 )
        {
          LastError = GetLastError();
          v10 = LastError;
          if ( LastError > 0 )
            v10 = (unsigned __int16)LastError | 0x80070000;
          goto LABEL_32;
        }
        if ( v8 > (unsigned __int64)v7 )
        {
          v10 = -2147024774;
LABEL_32:
          free(lpDst);
          return v10;
        }
        v11 = (unsigned __int64)(v7 + 11);
        if ( v7 + 11 >= v7 )
        {
          v12 = v7 + 141;
          if ( v11 + 260 >= v11 )
          {
            Block = 0;
            if ( !(unsigned __int8)ATL::CHeapPtr<unsigned short,ATL::CCRTAllocator>::Allocate(&Block, v11 + 260) )
            {
              free(Block);
              goto LABEL_15;
            }
            IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetImpl'::`2'::impl);
            v14 = *((_BYTE *)a2 + 85);
            v15 = L"/launchnarratorhome";
            if ( IsEnabled )
            {
              if ( !v14 )
                v15 = &qword_14002C590;
              v16 = L"/launchnarratorupdates";
              if ( !*((_BYTE *)a2 + 86) )
                v16 = &qword_14002C590;
              v17 = L"/hardwarebuttonlaunch";
              if ( !*((_BYTE *)a2 + 84) )
                v17 = &qword_14002C590;
              lpPreviousValue = v17;
              v18 = (unsigned __int64)v12;
              v19 = (WCHAR *)Block;
              v20 = StringCchPrintfW(
                      (unsigned __int16 *)Block,
                      v18,
                      L"%s /start %s %s %s %s",
                      lpDst,
                      *(_QWORD *)a2,
                      lpPreviousValue,
                      v16,
                      v15);
            }
            else
            {
              if ( !v14 )
                v15 = &qword_14002C590;
              v21 = L"/hardwarebuttonlaunch";
              if ( !*((_BYTE *)a2 + 84) )
                v21 = &qword_14002C590;
              lpPreviousValuea = v21;
              v22 = (unsigned __int64)v12;
              v19 = (WCHAR *)Block;
              v20 = StringCchPrintfW(
                      (unsigned __int16 *)Block,
                      v22,
                      L"%s /start %s %s %s",
                      lpDst,
                      *(_QWORD *)a2,
                      lpPreviousValuea,
                      v15);
            }
            if ( v20 >= 0 )
            {
              memset(&ProcessInformation, 0, sizeof(ProcessInformation));
              memset_0(&StartupInfo.cb + 1, 0, 0x6Cu);
              StartupInfo.cb = 112;
              Value = 0;
              v24 = 0;
              v25 = 0;
              Size = 0;
              if ( a3 )
              {
                if ( (int)GetShellProcessHandle(v23, &Value) >= 0 )
                {
                  InitializeProcThreadAttributeList(0, 1u, 0, &Size);
                  v26 = Size;
                  ProcessHeap = GetProcessHeap();
                  v28 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)HeapAlloc(ProcessHeap, 0, v26);
                  v25 = v28;
                  if ( v28 )
                  {
                    if ( InitializeProcThreadAttributeList(v28, 1u, 0, &Size) )
                    {
                      v24 = 1;
                      updated = UpdateProcThreadAttribute(v25, 0, 0x20000u, &Value, 8u, 0, 0);
                      v30 = v38;
                      if ( updated )
                        v30 = v25;
                      v38 = v30;
                    }
                  }
                }
              }
              if ( CreateProcessW(lpDst, v19, 0, 0, 0, 0x1080000u, 0, 0, &StartupInfo, &ProcessInformation) )
              {
                v10 = 0;
                CloseHandle(ProcessInformation.hProcess);
                CloseHandle(ProcessInformation.hThread);
              }
              else
              {
                v10 = -2147467259;
              }
              if ( v24 )
                DeleteProcThreadAttributeList(v25);
              if ( v25 )
              {
                v31 = GetProcessHeap();
                HeapFree(v31, 0, v25);
              }
              free(v19);
              goto LABEL_32;
            }
            free(v19);
          }
        }
        v10 = -2147467259;
        goto LABEL_32;
      }
LABEL_15:
      v10 = -2147024882;
      goto LABEL_32;
    }
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x140014844  mov     rax, rsp
0x140014847  mov     [rax+10h], rbx
0x14001484b  mov     [rax+18h], rsi
0x14001484f  mov     [rax+8], rcx
0x140014853  push    rbp
0x140014854  push    r12
0x140014856  push    r13
0x140014858  push    r14
0x14001485a  push    r15
0x14001485c  lea     rbp, [rax-5Fh]
0x140014860  sub     rsp, 0F0h
0x140014867  mov     r12d, r8d
0x14001486a  mov     rsi, rdx
0x14001486d  mov     rcx, rdx; this
0x140014870  call    ?IsRunning@Accommodation@@QEAAHXZ; Accommodation::IsRunning(void)
0x140014875  xor     r13d, r13d
0x140014878  test    eax, eax
0x14001487a  jz      short loc_140014883
0x14001487c  xor     eax, eax
0x14001487e  jmp     loc_140014BFF
0x140014883  mov     [rbp+57h+lpDst], r13
0x140014887  lea     r8, [rbp+57h+lpDst]; unsigned __int64 *
0x14001488b  lea     rcx, ?_atBrokerExe@StartList@@0PAGA; "%SystemRoot%\\System32\\ATBroker.exe"
0x140014892  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x140014897  test    eax, eax
0x140014899  js      loc_140014BFA
0x14001489f  mov     rax, [rbp+57h+lpDst]
0x1400148a3  lea     rbx, [rax+104h]
0x1400148aa  cmp     rbx, rax
0x1400148ad  jb      loc_140014BFA
0x1400148b3  mov     [rbp+57h+lpDst], r13
0x1400148b7  mov     rdx, rbx
0x1400148ba  lea     rcx, [rbp+57h+lpDst]
0x1400148be  call    ?Allocate@?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x1400148c3  test    al, al
0x1400148c5  jz      loc_14001495F
0x1400148cb  mov     r8d, ebx; nSize
0x1400148ce  mov     rdx, [rbp+57h+lpDst]; lpDst
0x1400148d2  lea     rcx, ?_atBrokerExe@StartList@@0PAGA; "%SystemRoot%\\System32\\ATBroker.exe"
0x1400148d9  call    cs:__imp_ExpandEnvironmentStringsW
0x1400148e0  nop     dword ptr [rax+rax+00h]
0x1400148e5  test    eax, eax
0x1400148e7  jnz     short loc_14001490D
0x1400148e9  call    cs:__imp_GetLastError
0x1400148f0  nop     dword ptr [rax+rax+00h]
0x1400148f5  mov     esi, eax
0x1400148f7  test    eax, eax
0x1400148f9  jle     loc_140014A36
0x1400148ff  movzx   esi, ax
0x140014902  or      esi, 80070000h
0x140014908  jmp     loc_140014A36
0x14001490d  mov     eax, eax
0x14001490f  cmp     rax, rbx
0x140014912  jbe     short loc_14001491E
0x140014914  mov     esi, 8007007Ah
0x140014919  jmp     loc_140014A36
0x14001491e  lea     rax, [rbx+16h]
0x140014922  cmp     rax, rbx
0x140014925  jb      loc_140014A31
0x14001492b  lea     rbx, [rax+104h]
0x140014932  cmp     rbx, rax
0x140014935  jb      loc_140014A31
0x14001493b  mov     [rbp+57h+Block], r13
0x14001493f  mov     rdx, rbx
0x140014942  lea     rcx, [rbp+57h+Block]
0x140014946  call    ?Allocate@?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x14001494b  test    al, al
0x14001494d  jnz     short loc_140014969
0x14001494f  mov     rcx, [rbp+57h+Block]; Block
0x140014953  call    cs:__imp_free
0x14001495a  nop     dword ptr [rax+rax+00h]
0x14001495f  mov     esi, 8007000Eh
0x140014964  jmp     loc_140014A36
0x140014969  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates> `wil::Feature<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetImpl(void)'::`2'::impl
0x140014970  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::__private_IsEnabled(void)
0x140014975  mov     dl, [rsi+55h]
0x140014978  lea     r8, qword_14002C590
0x14001497f  lea     rcx, aLaunchnarrator; "/launchnarratorhome"
0x140014986  mov     r9, [rbp+57h+lpDst]
0x14001498a  test    al, al
0x14001498c  jz      short loc_1400149E1
0x14001498e  test    dl, dl
0x140014990  cmovz   rcx, r8
0x140014994  lea     rax, aLaunchnarrator_0; "/launchnarratorupdates"
0x14001499b  cmp     [rsi+56h], r13b
0x14001499f  cmovz   rax, r8
0x1400149a3  lea     rdx, aHardwarebutton; "/hardwarebuttonlaunch"
0x1400149aa  cmp     [rsi+54h], r13b
0x1400149ae  cmovz   rdx, r8
0x1400149b2  mov     [rsp+110h+lpCurrentDirectory], rcx
0x1400149b7  mov     [rsp+110h+lpReturnSize], rax
0x1400149bc  mov     [rsp+110h+lpPreviousValue], rdx
0x1400149c1  mov     rax, [rsi]
0x1400149c4  mov     [rsp+110h+cbSize], rax
0x1400149c9  lea     r8, aSStartSSSS; "%s /start %s %s %s %s"
0x1400149d0  mov     rdx, rbx; unsigned __int64
0x1400149d3  mov     rbx, [rbp+57h+Block]
0x1400149d7  mov     rcx, rbx; unsigned __int16 *
0x1400149da  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400149df  jmp     short loc_140014A1E
0x1400149e1  test    dl, dl
0x1400149e3  cmovz   rcx, r8
0x1400149e7  lea     rdx, aHardwarebutton; "/hardwarebuttonlaunch"
0x1400149ee  cmp     [rsi+54h], r13b
0x1400149f2  cmovz   rdx, r8
0x1400149f6  mov     [rsp+110h+lpReturnSize], rcx
0x1400149fb  mov     [rsp+110h+lpPreviousValue], rdx
0x140014a00  mov     rax, [rsi]
0x140014a03  mov     [rsp+110h+cbSize], rax
0x140014a08  lea     r8, aSStartSSS; "%s /start %s %s %s"
0x140014a0f  mov     rdx, rbx; unsigned __int64
0x140014a12  mov     rbx, [rbp+57h+Block]
0x140014a16  mov     rcx, rbx; unsigned __int16 *
0x140014a19  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140014a1e  test    eax, eax
0x140014a20  jns     short loc_140014A4D
0x140014a22  mov     rcx, rbx; Block
0x140014a25  call    cs:__imp_free
0x140014a2c  nop     dword ptr [rax+rax+00h]
0x140014a31  mov     esi, 80004005h
0x140014a36  mov     rcx, [rbp+57h+lpDst]; Block
0x140014a3a  call    cs:__imp_free
0x140014a41  nop     dword ptr [rax+rax+00h]
0x140014a46  mov     eax, esi
0x140014a48  jmp     loc_140014BFF
0x140014a4d  xorps   xmm0, xmm0
0x140014a50  xor     eax, eax
0x140014a52  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x140014a56  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x140014a5a  xor     edx, edx; Val
0x140014a5c  lea     r8d, [rax+6Ch]; Size
0x140014a60  lea     rcx, [rbp+57h+StartupInfo+4]; void *
0x140014a64  call    memset_0
0x140014a69  mov     [rbp+57h+StartupInfo.cb], 70h ; 'p'
0x140014a70  mov     [rbp+57h+Value], r13
0x140014a74  mov     r15d, r13d
0x140014a77  mov     r14, r13
0x140014a7a  mov     [rbp+57h+Size], r13
0x140014a7e  test    r12d, r12d
0x140014a81  jz      loc_140014B3C
0x140014a87  lea     rdx, [rbp+57h+Value]; void **
0x140014a8b  call    ?GetShellProcessHandle@@YAJKPEAPEAX@Z; GetShellProcessHandle(ulong,void * *)
0x140014a90  test    eax, eax
0x140014a92  js      loc_140014B3C
0x140014a98  lea     r9, [rbp+57h+Size]; lpSize
0x140014a9c  xor     r8d, r8d; dwFlags
0x140014a9f  lea     r12d, [r8+1]
0x140014aa3  mov     edx, r12d; dwAttributeCount
0x140014aa6  xor     ecx, ecx; lpAttributeList
0x140014aa8  call    cs:__imp_InitializeProcThreadAttributeList
0x140014aaf  nop     dword ptr [rax+rax+00h]
0x140014ab4  mov     rsi, [rbp+57h+Size]
0x140014ab8  call    cs:__imp_GetProcessHeap
0x140014abf  nop     dword ptr [rax+rax+00h]
0x140014ac4  mov     r8, rsi; dwBytes
0x140014ac7  xor     edx, edx; dwFlags
0x140014ac9  mov     rcx, rax; hHeap
0x140014acc  call    cs:__imp_HeapAlloc
0x140014ad3  nop     dword ptr [rax+rax+00h]
0x140014ad8  mov     r14, rax
0x140014adb  test    rax, rax
0x140014ade  jz      short loc_140014B3C
0x140014ae0  lea     r9, [rbp+57h+Size]; lpSize
0x140014ae4  xor     r8d, r8d; dwFlags
0x140014ae7  mov     edx, r12d; dwAttributeCount
0x140014aea  mov     rcx, rax; lpAttributeList
0x140014aed  call    cs:__imp_InitializeProcThreadAttributeList
0x140014af4  nop     dword ptr [rax+rax+00h]
0x140014af9  test    eax, eax
0x140014afb  jz      short loc_140014B3C
0x140014afd  mov     r15d, r12d
0x140014b00  mov     [rsp+110h+lpReturnSize], r13; lpReturnSize
0x140014b05  mov     [rsp+110h+lpPreviousValue], r13; lpPreviousValue
0x140014b0a  mov     [rsp+110h+cbSize], 8; cbSize
0x140014b13  lea     r9, [rbp+57h+Value]; lpValue
0x140014b17  xor     edx, edx; dwFlags
0x140014b19  mov     r8d, 20000h; Attribute
0x140014b1f  mov     rcx, r14; lpAttributeList
0x140014b22  call    cs:__imp_UpdateProcThreadAttribute
0x140014b29  nop     dword ptr [rax+rax+00h]
0x140014b2e  mov     rcx, [rbp+57h+var_28]
0x140014b32  test    eax, eax
0x140014b34  cmovnz  rcx, r14
0x140014b38  mov     [rbp+57h+var_28], rcx
0x140014b3c  lea     rax, [rbp+57h+ProcessInformation]
0x140014b40  mov     [rsp+110h+lpProcessInformation], rax; lpProcessInformation
0x140014b45  lea     rax, [rbp+57h+StartupInfo]
0x140014b49  mov     [rsp+110h+lpStartupInfo], rax; lpStartupInfo
0x140014b4e  mov     [rsp+110h+lpCurrentDirectory], r13; lpCurrentDirectory
0x140014b53  mov     [rsp+110h+lpReturnSize], r13; lpEnvironment
0x140014b58  mov     dword ptr [rsp+110h+lpPreviousValue], 1080000h; dwCreationFlags
0x140014b60  mov     dword ptr [rsp+110h+cbSize], r13d; bInheritHandles
0x140014b65  xor     r9d, r9d; lpThreadAttributes
0x140014b68  xor     r8d, r8d; lpProcessAttributes
0x140014b6b  mov     rdx, rbx; lpCommandLine
0x140014b6e  mov     rcx, [rbp+57h+lpDst]; lpApplicationName
0x140014b72  call    cs:__imp_CreateProcessW
0x140014b79  nop     dword ptr [rax+rax+00h]
0x140014b7e  test    eax, eax
0x140014b80  jz      short loc_140014BA7
0x140014b82  mov     esi, r13d
0x140014b85  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hObject
0x140014b89  call    cs:__imp_CloseHandle
0x140014b90  nop     dword ptr [rax+rax+00h]
0x140014b95  mov     rcx, [rbp+57h+ProcessInformation.hThread]; hObject
0x140014b99  call    cs:__imp_CloseHandle
0x140014ba0  nop     dword ptr [rax+rax+00h]
0x140014ba5  jmp     short loc_140014BAC
0x140014ba7  mov     esi, 80004005h
0x140014bac  test    r15d, r15d
0x140014baf  jz      short loc_140014BC0
0x140014bb1  mov     rcx, r14; lpAttributeList
0x140014bb4  call    cs:__imp_DeleteProcThreadAttributeList
0x140014bbb  nop     dword ptr [rax+rax+00h]
0x140014bc0  test    r14, r14
0x140014bc3  jz      short loc_140014BE6
0x140014bc5  call    cs:__imp_GetProcessHeap
0x140014bcc  nop     dword ptr [rax+rax+00h]
0x140014bd1  mov     rcx, rax; hHeap
0x140014bd4  mov     r8, r14; lpMem
0x140014bd7  xor     edx, edx; dwFlags
0x140014bd9  call    cs:__imp_HeapFree
0x140014be0  nop     dword ptr [rax+rax+00h]
0x140014be5  nop
0x140014be6  mov     rcx, rbx; Block
0x140014be9  call    cs:__imp_free
0x140014bf0  nop     dword ptr [rax+rax+00h]
0x140014bf5  jmp     loc_140014A36
0x140014bfa  mov     eax, 80004005h
0x140014bff  lea     r11, [rsp+110h+var_20]
0x140014c07  mov     rbx, [r11+38h]
0x140014c0b  mov     rsi, [r11+40h]
0x140014c0f  mov     rsp, r11
0x140014c12  pop     r15
0x140014c14  pop     r14
0x140014c16  pop     r13
0x140014c18  pop     r12
0x140014c1a  pop     rbp
0x140014c1b  retn
```
