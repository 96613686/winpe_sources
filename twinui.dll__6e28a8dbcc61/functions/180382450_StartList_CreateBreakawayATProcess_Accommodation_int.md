# StartList::CreateBreakawayATProcess(Accommodation *,int)

- ea: `0x180382450`
- end: `0x1803827c7`
- name: `?CreateBreakawayATProcess@StartList@@AEAAJPEAVAccommodation@@H@Z`
- size: `887`
- prototype: `int(StartList *__hidden this, struct Accommodation *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180383f98`

## callees

- `0x18004719c`
- `0x1801321ac`
- `0x18013df8c`
- `0x180380d00`
- `0x180381538`
- `0x180381e08`
- `0x180382450`
- `0x180382a00`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180382558`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180382624`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180382633`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18038279a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180382558`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180382624`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180382633`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18038279a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1803826b3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1803826b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180382790`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180382790`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1803826a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180382782`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1803826a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180382782`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803824f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803824f4`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x180382777`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x180382777`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1803826fd`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1803826fd`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18038269b`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1803826ce`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18038269b`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1803826ce`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180382747`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180382747`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180382758`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180382762`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180382758`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180382762`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1803824ea`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1803824ea`

## string_xrefs

- `0x180382593`: `/launchnarratorupdates`
- `0x18038249c`: `%SystemRoot%\System32\ATBroker.exe`
- `0x1803824e3`: `%SystemRoot%\System32\ATBroker.exe`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StartList::CreateBreakawayATProcess(WCHAR *this, struct Accommodation *a2, int a3)
{
  LPWSTR v6; // rbx
  DWORD v7; // eax
  signed int LastError; // eax
  unsigned int v9; // esi
  unsigned __int64 v10; // rax
  LPWSTR v11; // rbx
  char IsEnabled; // al
  char v13; // dl
  const wchar_t *v14; // rcx
  const wchar_t *v15; // rax
  const WCHAR *v16; // rdx
  unsigned __int64 v17; // rdx
  WCHAR *v18; // rbx
  int v19; // eax
  const WCHAR *v20; // rdx
  unsigned __int64 v21; // rdx
  unsigned int v22; // ecx
  int v23; // r15d
  struct _PROC_THREAD_ATTRIBUTE_LIST *v24; // r14
  SIZE_T v25; // rsi
  HANDLE ProcessHeap; // rax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v27; // rax
  BOOL updated; // eax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v29; // rcx
  HANDLE v30; // rax
  const WCHAR *lpPreviousValue; // [rsp+30h] [rbp-91h]
  const WCHAR *lpPreviousValuea; // [rsp+30h] [rbp-91h]
  ULONG_PTR Size; // [rsp+58h] [rbp-69h] BYREF
  void *Value; // [rsp+60h] [rbp-61h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+68h] [rbp-59h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+88h] [rbp-39h] BYREF
  struct _PROC_THREAD_ATTRIBUTE_LIST *v37; // [rsp+F0h] [rbp+2Fh]
  LPWSTR lpDst; // [rsp+128h] [rbp+67h] BYREF
  void *Block; // [rsp+140h] [rbp+7Fh] BYREF

  lpDst = this;
  if ( (unsigned int)Accommodation::IsRunning(a2) )
    return 0;
  lpDst = 0;
  if ( (int)StringCchLengthW(StartList::_atBrokerExe, 0x7FFFFFFFu, (unsigned __int64 *)&lpDst) >= 0 )
  {
    v6 = lpDst + 130;
    if ( lpDst + 130 >= lpDst )
    {
      lpDst = 0;
      if ( (unsigned __int8)ATL::CHeapPtr<unsigned short,ATL::CCRTAllocator>::Allocate(&lpDst, v6) )
      {
        v7 = ExpandEnvironmentStringsW(StartList::_atBrokerExe, lpDst, (DWORD)v6);
        if ( !v7 )
        {
          LastError = GetLastError();
          v9 = LastError;
          if ( LastError > 0 )
            v9 = (unsigned __int16)LastError | 0x80070000;
          goto LABEL_32;
        }
        if ( v7 > (unsigned __int64)v6 )
        {
          v9 = -2147024774;
LABEL_32:
          free(lpDst);
          return v9;
        }
        v10 = (unsigned __int64)(v6 + 11);
        if ( v6 + 11 >= v6 )
        {
          v11 = v6 + 141;
          if ( v10 + 260 >= v10 )
          {
            Block = 0;
            if ( !(unsigned __int8)ATL::CHeapPtr<unsigned short,ATL::CCRTAllocator>::Allocate(&Block, v10 + 260) )
            {
              free(Block);
              goto LABEL_15;
            }
            IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetImpl'::`2'::impl);
            v13 = *((_BYTE *)a2 + 85);
            v14 = L"/launchnarratorhome";
            if ( IsEnabled )
            {
              if ( !v13 )
                v14 = &pszDefault;
              v15 = L"/launchnarratorupdates";
              if ( !*((_BYTE *)a2 + 86) )
                v15 = &pszDefault;
              v16 = L"/hardwarebuttonlaunch";
              if ( !*((_BYTE *)a2 + 84) )
                v16 = &pszDefault;
              lpPreviousValue = v16;
              v17 = (unsigned __int64)v11;
              v18 = (WCHAR *)Block;
              v19 = StringCchPrintfW(
                      (unsigned __int16 *)Block,
                      v17,
                      L"%s /start %s %s %s %s",
                      lpDst,
                      *(_QWORD *)a2,
                      lpPreviousValue,
                      v15,
                      v14);
            }
            else
            {
              if ( !v13 )
                v14 = &pszDefault;
              v20 = L"/hardwarebuttonlaunch";
              if ( !*((_BYTE *)a2 + 84) )
                v20 = &pszDefault;
              lpPreviousValuea = v20;
              v21 = (unsigned __int64)v11;
              v18 = (WCHAR *)Block;
              v19 = StringCchPrintfW(
                      (unsigned __int16 *)Block,
                      v21,
                      L"%s /start %s %s %s",
                      lpDst,
                      *(_QWORD *)a2,
                      lpPreviousValuea,
                      v14);
            }
            if ( v19 >= 0 )
            {
              memset(&ProcessInformation, 0, sizeof(ProcessInformation));
              memset_0(&StartupInfo.cb + 1, 0, 0x6Cu);
              StartupInfo.cb = 112;
              Value = 0;
              v23 = 0;
              v24 = 0;
              Size = 0;
              if ( a3 )
              {
                if ( (int)GetShellProcessHandle(v22, &Value) >= 0 )
                {
                  InitializeProcThreadAttributeList(0, 1u, 0, &Size);
                  v25 = Size;
                  ProcessHeap = GetProcessHeap();
                  v27 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)HeapAlloc(ProcessHeap, 0, v25);
                  v24 = v27;
                  if ( v27 )
                  {
                    if ( InitializeProcThreadAttributeList(v27, 1u, 0, &Size) )
                    {
                      v23 = 1;
                      updated = UpdateProcThreadAttribute(v24, 0, 0x20000u, &Value, 8u, 0, 0);
                      v29 = v37;
                      if ( updated )
                        v29 = v24;
                      v37 = v29;
                    }
                  }
                }
              }
              if ( CreateProcessW(lpDst, v18, 0, 0, 0, 0x1080000u, 0, 0, &StartupInfo, &ProcessInformation) )
              {
                v9 = 0;
                CloseHandle(ProcessInformation.hProcess);
                CloseHandle(ProcessInformation.hThread);
              }
              else
              {
                v9 = -2147467259;
              }
              if ( v23 )
                DeleteProcThreadAttributeList(v24);
              if ( v24 )
              {
                v30 = GetProcessHeap();
                HeapFree(v30, 0, v24);
              }
              free(v18);
              goto LABEL_32;
            }
            free(v18);
          }
        }
        v9 = -2147467259;
        goto LABEL_32;
      }
LABEL_15:
      v9 = -2147024882;
      goto LABEL_32;
    }
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x180382450  mov     rax, rsp
0x180382453  mov     [rax+10h], rbx
0x180382457  mov     [rax+18h], rsi
0x18038245b  mov     [rax+8], rcx
0x18038245f  push    rbp
0x180382460  push    r12
0x180382462  push    r13
0x180382464  push    r14
0x180382466  push    r15
0x180382468  lea     rbp, [rax-5Fh]
0x18038246c  sub     rsp, 0F0h
0x180382473  mov     r12d, r8d
0x180382476  mov     rsi, rdx
0x180382479  mov     rcx, rdx; this
0x18038247c  call    ?IsRunning@Accommodation@@QEAAHXZ; Accommodation::IsRunning(void)
0x180382481  xor     r13d, r13d
0x180382484  test    eax, eax
0x180382486  jz      short loc_18038248F
0x180382488  xor     eax, eax
0x18038248a  jmp     loc_1803827AA
0x18038248f  mov     [rbp+57h+lpDst], r13
0x180382493  lea     r8, [rbp+57h+lpDst]; unsigned __int64 *
0x180382497  mov     edx, 7FFFFFFFh; unsigned __int64
0x18038249c  lea     rcx, ?_atBrokerExe@StartList@@0PAGA; "%SystemRoot%\\System32\\ATBroker.exe"
0x1803824a3  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1803824a8  test    eax, eax
0x1803824aa  js      loc_1803827A5
0x1803824b0  mov     rax, [rbp+57h+lpDst]
0x1803824b4  lea     rbx, [rax+104h]
0x1803824bb  cmp     rbx, rax
0x1803824be  jb      loc_1803827A5
0x1803824c4  mov     [rbp+57h+lpDst], r13
0x1803824c8  mov     rdx, rbx
0x1803824cb  lea     rcx, [rbp+57h+lpDst]
0x1803824cf  call    ?Allocate@?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x1803824d4  test    al, al
0x1803824d6  jz      loc_18038255E
0x1803824dc  mov     r8d, ebx; nSize
0x1803824df  mov     rdx, [rbp+57h+lpDst]; lpDst
0x1803824e3  lea     rcx, ?_atBrokerExe@StartList@@0PAGA; "%SystemRoot%\\System32\\ATBroker.exe"
0x1803824ea  call    cs:__imp_ExpandEnvironmentStringsW
0x1803824f0  test    eax, eax
0x1803824f2  jnz     short loc_180382512
0x1803824f4  call    cs:__imp_GetLastError
0x1803824fa  mov     esi, eax
0x1803824fc  test    eax, eax
0x1803824fe  jle     loc_18038262F
0x180382504  movzx   esi, ax
0x180382507  or      esi, 80070000h
0x18038250d  jmp     loc_18038262F
0x180382512  mov     eax, eax
0x180382514  cmp     rax, rbx
0x180382517  jbe     short loc_180382523
0x180382519  mov     esi, 8007007Ah
0x18038251e  jmp     loc_18038262F
0x180382523  lea     rax, [rbx+16h]
0x180382527  cmp     rax, rbx
0x18038252a  jb      loc_18038262A
0x180382530  lea     rbx, [rax+104h]
0x180382537  cmp     rbx, rax
0x18038253a  jb      loc_18038262A
0x180382540  mov     [rbp+57h+Block], r13
0x180382544  mov     rdx, rbx
0x180382547  lea     rcx, [rbp+57h+Block]
0x18038254b  call    ?Allocate@?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x180382550  test    al, al
0x180382552  jnz     short loc_180382568
0x180382554  mov     rcx, [rbp+57h+Block]; Block
0x180382558  call    cs:__imp_free
0x18038255e  mov     esi, 8007000Eh
0x180382563  jmp     loc_18038262F
0x180382568  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates> `wil::Feature<__WilFeatureTraits_Feature_Narrator_AddUpdates>::GetImpl(void)'::`2'::impl
0x18038256f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Narrator_AddUpdates@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Narrator_AddUpdates>::__private_IsEnabled(void)
0x180382574  mov     dl, [rsi+55h]
0x180382577  lea     r8, pszDefault
0x18038257e  lea     rcx, aLaunchnarrator; "/launchnarratorhome"
0x180382585  mov     r9, [rbp+57h+lpDst]
0x180382589  test    al, al
0x18038258b  jz      short loc_1803825E0
0x18038258d  test    dl, dl
0x18038258f  cmovz   rcx, r8
0x180382593  lea     rax, aLaunchnarrator_0; "/launchnarratorupdates"
0x18038259a  cmp     [rsi+56h], r13b
0x18038259e  cmovz   rax, r8
0x1803825a2  lea     rdx, aHardwarebutton_0; "/hardwarebuttonlaunch"
0x1803825a9  cmp     [rsi+54h], r13b
0x1803825ad  cmovz   rdx, r8
0x1803825b1  mov     [rsp+110h+lpCurrentDirectory], rcx
0x1803825b6  mov     [rsp+110h+lpReturnSize], rax
0x1803825bb  mov     [rsp+110h+lpPreviousValue], rdx
0x1803825c0  mov     rax, [rsi]
0x1803825c3  mov     [rsp+110h+cbSize], rax
0x1803825c8  lea     r8, aSStartSSSS; "%s /start %s %s %s %s"
0x1803825cf  mov     rdx, rbx; unsigned __int64
0x1803825d2  mov     rbx, [rbp+57h+Block]
0x1803825d6  mov     rcx, rbx; unsigned __int16 *
0x1803825d9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1803825de  jmp     short loc_18038261D
0x1803825e0  test    dl, dl
0x1803825e2  cmovz   rcx, r8
0x1803825e6  lea     rdx, aHardwarebutton_0; "/hardwarebuttonlaunch"
0x1803825ed  cmp     [rsi+54h], r13b
0x1803825f1  cmovz   rdx, r8
0x1803825f5  mov     [rsp+110h+lpReturnSize], rcx
0x1803825fa  mov     [rsp+110h+lpPreviousValue], rdx
0x1803825ff  mov     rax, [rsi]
0x180382602  mov     [rsp+110h+cbSize], rax
0x180382607  lea     r8, aSStartSSS; "%s /start %s %s %s"
0x18038260e  mov     rdx, rbx; unsigned __int64
0x180382611  mov     rbx, [rbp+57h+Block]
0x180382615  mov     rcx, rbx; unsigned __int16 *
0x180382618  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18038261d  test    eax, eax
0x18038261f  jns     short loc_180382640
0x180382621  mov     rcx, rbx; Block
0x180382624  call    cs:__imp_free
0x18038262a  mov     esi, 80004005h
0x18038262f  mov     rcx, [rbp+57h+lpDst]; Block
0x180382633  call    cs:__imp_free
0x180382639  mov     eax, esi
0x18038263b  jmp     loc_1803827AA
0x180382640  xorps   xmm0, xmm0
0x180382643  xor     eax, eax
0x180382645  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x180382649  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x18038264d  xor     edx, edx; Val
0x18038264f  lea     r8d, [rax+6Ch]; Size
0x180382653  lea     rcx, [rbp+57h+StartupInfo+4]; void *
0x180382657  call    memset_0
0x18038265c  mov     [rbp+57h+StartupInfo.cb], 70h ; 'p'
0x180382663  mov     [rbp+57h+Value], r13
0x180382667  mov     r15d, r13d
0x18038266a  mov     r14, r13
0x18038266d  mov     [rbp+57h+Size], r13
0x180382671  test    r12d, r12d
0x180382674  jz      loc_180382711
0x18038267a  lea     rdx, [rbp+57h+Value]; void **
0x18038267e  call    ?GetShellProcessHandle@@YAJKPEAPEAX@Z; GetShellProcessHandle(ulong,void * *)
0x180382683  test    eax, eax
0x180382685  js      loc_180382711
0x18038268b  lea     r9, [rbp+57h+Size]; lpSize
0x18038268f  xor     r8d, r8d; dwFlags
0x180382692  lea     r12d, [r8+1]
0x180382696  mov     edx, r12d; dwAttributeCount
0x180382699  xor     ecx, ecx; lpAttributeList
0x18038269b  call    cs:__imp_InitializeProcThreadAttributeList
0x1803826a1  mov     rsi, [rbp+57h+Size]
0x1803826a5  call    cs:__imp_GetProcessHeap
0x1803826ab  mov     r8, rsi; dwBytes
0x1803826ae  xor     edx, edx; dwFlags
0x1803826b0  mov     rcx, rax; hHeap
0x1803826b3  call    cs:__imp_HeapAlloc
0x1803826b9  mov     r14, rax
0x1803826bc  test    rax, rax
0x1803826bf  jz      short loc_180382711
0x1803826c1  lea     r9, [rbp+57h+Size]; lpSize
0x1803826c5  xor     r8d, r8d; dwFlags
0x1803826c8  mov     edx, r12d; dwAttributeCount
0x1803826cb  mov     rcx, rax; lpAttributeList
0x1803826ce  call    cs:__imp_InitializeProcThreadAttributeList
0x1803826d4  test    eax, eax
0x1803826d6  jz      short loc_180382711
0x1803826d8  mov     r15d, r12d
0x1803826db  mov     [rsp+110h+lpReturnSize], r13; lpReturnSize
0x1803826e0  mov     [rsp+110h+lpPreviousValue], r13; lpPreviousValue
0x1803826e5  mov     [rsp+110h+cbSize], 8; cbSize
0x1803826ee  lea     r9, [rbp+57h+Value]; lpValue
0x1803826f2  xor     edx, edx; dwFlags
0x1803826f4  mov     r8d, 20000h; Attribute
0x1803826fa  mov     rcx, r14; lpAttributeList
0x1803826fd  call    cs:__imp_UpdateProcThreadAttribute
0x180382703  mov     rcx, [rbp+57h+var_28]
0x180382707  test    eax, eax
0x180382709  cmovnz  rcx, r14
0x18038270d  mov     [rbp+57h+var_28], rcx
0x180382711  lea     rax, [rbp+57h+ProcessInformation]
0x180382715  mov     [rsp+110h+lpProcessInformation], rax; lpProcessInformation
0x18038271a  lea     rax, [rbp+57h+StartupInfo]
0x18038271e  mov     [rsp+110h+lpStartupInfo], rax; lpStartupInfo
0x180382723  mov     [rsp+110h+lpCurrentDirectory], r13; lpCurrentDirectory
0x180382728  mov     [rsp+110h+lpReturnSize], r13; lpEnvironment
0x18038272d  mov     dword ptr [rsp+110h+lpPreviousValue], 1080000h; dwCreationFlags
0x180382735  mov     dword ptr [rsp+110h+cbSize], r13d; bInheritHandles
0x18038273a  xor     r9d, r9d; lpThreadAttributes
0x18038273d  xor     r8d, r8d; lpProcessAttributes
0x180382740  mov     rdx, rbx; lpCommandLine
0x180382743  mov     rcx, [rbp+57h+lpDst]; lpApplicationName
0x180382747  call    cs:__imp_CreateProcessW
0x18038274d  test    eax, eax
0x18038274f  jz      short loc_18038276A
0x180382751  mov     esi, r13d
0x180382754  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hObject
0x180382758  call    cs:__imp_CloseHandle
0x18038275e  mov     rcx, [rbp+57h+ProcessInformation.hThread]; hObject
0x180382762  call    cs:__imp_CloseHandle
0x180382768  jmp     short loc_18038276F
0x18038276a  mov     esi, 80004005h
0x18038276f  test    r15d, r15d
0x180382772  jz      short loc_18038277D
0x180382774  mov     rcx, r14; lpAttributeList
0x180382777  call    cs:__imp_DeleteProcThreadAttributeList
0x18038277d  test    r14, r14
0x180382780  jz      short loc_180382797
0x180382782  call    cs:__imp_GetProcessHeap
0x180382788  mov     rcx, rax; hHeap
0x18038278b  mov     r8, r14; lpMem
0x18038278e  xor     edx, edx; dwFlags
0x180382790  call    cs:__imp_HeapFree
0x180382796  nop
0x180382797  mov     rcx, rbx; Block
0x18038279a  call    cs:__imp_free
0x1803827a0  jmp     loc_18038262F
0x1803827a5  mov     eax, 80004005h
0x1803827aa  lea     r11, [rsp+110h+var_20]
0x1803827b2  mov     rbx, [r11+38h]
0x1803827b6  mov     rsi, [r11+40h]
0x1803827ba  mov     rsp, r11
0x1803827bd  pop     r15
0x1803827bf  pop     r14
0x1803827c1  pop     r13
0x1803827c3  pop     r12
0x1803827c5  pop     rbp
0x1803827c6  retn
```
