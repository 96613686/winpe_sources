# __Trace::get_logfile(ushort const *)

- ea: `0x18001ac90`
- end: `0x18001b08a`
- name: `?get_logfile@__Trace@@QEAAPEAXPEBG@Z`
- size: `1018`
- prototype: `void *(__Trace *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18001a84c`

## callees

- `0x180011e40`
- `0x180013564`
- `0x180014120`
- `0x1800154d0`
- `0x18001ac90`
- `0x18001b0e8`
- `0x18001b1f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001ad45`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001ad45`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001ad33`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001ae15`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b066`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b07e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001ad33`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001ae15`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b066`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b07e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ae4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001af88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001afac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b074`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ae4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001af88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001afac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b074`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ae1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ae1b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001ae2d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001ae2d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001adfb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001adfb`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18001ad03`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18001ad03`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18001ad22`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18001ad22`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001af5a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001af5a`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18001af74`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18001af74`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001aee3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18001aee3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall __Trace::get_logfile(__Trace *this, const unsigned __int16 *a2)
{
  void **v3; // rcx
  __int64 FileW; // rbx
  char v5; // si
  HANDLE v6; // rdi
  BOOL v7; // eax
  void *v8; // rcx
  _LARGE_INTEGER v9; // r14
  __int64 v10; // rax
  WCHAR *v11; // rcx
  __int64 v12; // rdx
  WCHAR *v13; // r8
  WCHAR v14; // r9
  unsigned int v15; // ebx
  WCHAR *v16; // rcx
  int v17; // eax
  unsigned int v18; // ebx
  int v20; // eax
  unsigned int v21; // esi
  int v22; // eax
  int v23; // eax
  unsigned int v24; // esi
  HANDLE hObject; // [rsp+40h] [rbp-10h] BYREF
  int v26; // [rsp+48h] [rbp-8h]
  char v27; // [rsp+4Ch] [rbp-4h]
  _LARGE_INTEGER FileSize; // [rsp+80h] [rbp+30h] BYREF
  HANDLE v29; // [rsp+90h] [rbp+40h]

  FileSize.QuadPart = (LONGLONG)this;
  AutoRevert::AutoRevert(&hObject);
  if ( v27 )
  {
    FileW = -1;
    v5 = 0;
    while ( !v5 )
    {
      while ( FileW == -1 )
      {
        if ( WaitForSingleObject(::hObject, 0xFFFFFFFF) == -1 )
          goto LABEL_36;
        v10 = 2147483646;
        v11 = &PathName;
        v12 = 261;
        v13 = ExistingFileName;
        do
        {
          if ( !v10 )
            break;
          v14 = *v11;
          if ( !*v11 )
            break;
          ++v11;
          *v13++ = v14;
          --v10;
          --v12;
        }
        while ( v12 );
        v15 = v12 == 0 ? 0x8007007A : 0;
        v16 = v13 - 1;
        if ( v12 )
          v16 = v13;
        *v16 = 0;
        if ( !v12 )
        {
          CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v15);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_a66c463c75c73635afca8e74831cc57c_Traceguids, v15);
          }
        }
        v17 = StringCchCatW(ExistingFileName, 0x105u, a2);
        v18 = v17;
        if ( v17 < 0 )
        {
          CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v17);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_a66c463c75c73635afca8e74831cc57c_Traceguids, v18);
          }
        }
        FileW = (__int64)CreateFileW(ExistingFileName, 0x40000000u, 5u, 0, 4u, 0x2080u, 0);
        if ( FileW == -1 )
        {
          ReleaseMutex(::hObject);
          if ( GetLastError() != 32 )
            goto LABEL_36;
          Sleep(0x14u);
        }
      }
      v6 = ::hObject;
      v29 = ::hObject;
      FileSize.QuadPart = 0;
      v7 = SetFilePointerEx((HANDLE)FileW, 0, 0, 2u);
      v8 = (void *)FileW;
      if ( !v7 )
        goto LABEL_50;
      v5 = 1;
      v9.QuadPart = dword_180068B84;
      if ( GetFileSizeEx((HANDLE)FileW, &FileSize) && FileSize.QuadPart > v9.QuadPart )
      {
        v20 = StringCchCopyW(NewFileName, 0x105u, ExistingFileName);
        v21 = v20;
        if ( v20 < 0 )
        {
          CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v20);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_a66c463c75c73635afca8e74831cc57c_Traceguids, v21);
          }
        }
        v22 = lstrlenW(NewFileName);
        v23 = StringCchCopyW(&word_18006A590[v22], 0x105u, L"lo_");
        v24 = v23;
        if ( v23 < 0 )
        {
          CMemoryLog::Write((CMemoryLog *)&unk_18006A9C0, v23);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_a66c463c75c73635afca8e74831cc57c_Traceguids, v24);
          }
        }
        DeleteFileW(NewFileName);
        if ( !MoveFileExW(ExistingFileName, NewFileName, 2u) )
        {
          if ( FileSize.QuadPart >= 2 * v9.QuadPart )
          {
            v8 = (void *)FileW;
LABEL_50:
            CloseHandle(v8);
            ReleaseMutex(v6);
            goto LABEL_36;
          }
          ReleaseMutex(v6);
          break;
        }
        v5 = 0;
        CloseHandle((HANDLE)FileW);
        FileW = -1;
      }
      ReleaseMutex(v6);
    }
    if ( hObject )
    {
      v26 = DLSetThreadToken(v3, hObject);
      CloseHandle(hObject);
    }
    return FileW;
  }
  else
  {
LABEL_36:
    if ( hObject )
    {
      v26 = DLSetThreadToken(v3, hObject);
      CloseHandle(hObject);
    }
    return -1;
  }
}

```

## disassembly

```asm
0x18001ac90  mov     [rsp-28h+arg_8], rbx
0x18001ac95  mov     [rsp-28h+arg_18], rsi
0x18001ac9a  mov     qword ptr [rsp-28h+FileSize], rcx
0x18001ac9f  push    rbp
0x18001aca0  push    rdi
0x18001aca1  push    r12
0x18001aca3  push    r14
0x18001aca5  push    r15
0x18001aca7  mov     rbp, rsp
0x18001acaa  sub     rsp, 50h
0x18001acae  mov     r15, rdx
0x18001acb1  lea     rcx, [rbp+hObject]; this
0x18001acb5  call    ??0AutoRevert@@QEAA@XZ; AutoRevert::AutoRevert(void)
0x18001acba  nop
0x18001acbb  xor     r12d, r12d
0x18001acbe  cmp     [rbp+var_4], r12b
0x18001acc2  jz      loc_18001AF97
0x18001acc8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001accc  mov     sil, r12b
0x18001accf  lea     rdi, WPP_GLOBAL_Control
0x18001acd6  test    sil, sil
0x18001acd9  jnz     loc_18001AE38
0x18001acdf  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001ace3  jz      short loc_18001AD3B
0x18001ace5  mov     rdi, cs:hObject
0x18001acec  mov     [rbp+arg_10], rdi
0x18001acf0  mov     rdx, r12; liDistanceToMove
0x18001acf3  mov     qword ptr [rbp+FileSize], rdx
0x18001acf7  mov     r9d, 2; dwMoveMethod
0x18001acfd  xor     r8d, r8d; lpNewFilePointer
0x18001ad00  mov     rcx, rbx; hFile
0x18001ad03  call    cs:__imp_SetFilePointerEx
0x18001ad09  mov     rcx, rbx; hFile
0x18001ad0c  test    eax, eax
0x18001ad0e  jz      loc_18001B074
0x18001ad14  mov     sil, 1
0x18001ad17  mov     r14d, cs:dword_180068B84
0x18001ad1e  lea     rdx, [rbp+FileSize]; lpFileSize
0x18001ad22  call    cs:__imp_GetFileSizeEx
0x18001ad28  test    eax, eax
0x18001ad2a  jnz     loc_18001AE6F
0x18001ad30  mov     rcx, rdi; hMutex
0x18001ad33  call    cs:__imp_ReleaseMutex
0x18001ad39  jmp     short loc_18001ACCF
0x18001ad3b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001ad3e  mov     rcx, cs:hObject; hHandle
0x18001ad45  call    cs:__imp_WaitForSingleObject
0x18001ad4b  cmp     eax, 0FFFFFFFFh
0x18001ad4e  jz      loc_18001AF97
0x18001ad54  mov     eax, 7FFFFFFEh
0x18001ad59  lea     rcx, PathName
0x18001ad60  mov     edx, 105h
0x18001ad65  lea     r8, ExistingFileName
0x18001ad6c  test    rax, rax
0x18001ad6f  jz      short loc_18001AD90
0x18001ad71  movzx   r9d, word ptr [rcx]
0x18001ad75  test    r9w, r9w
0x18001ad79  jz      short loc_18001AD90
0x18001ad7b  add     rcx, 2
0x18001ad7f  mov     [r8], r9w
0x18001ad83  add     r8, 2
0x18001ad87  dec     rax
0x18001ad8a  sub     rdx, 1
0x18001ad8e  jnz     short loc_18001AD6C
0x18001ad90  mov     rax, rdx
0x18001ad93  neg     rax
0x18001ad96  sbb     ebx, ebx
0x18001ad98  not     ebx
0x18001ad9a  and     ebx, 8007007Ah
0x18001ada0  lea     rcx, [r8-2]
0x18001ada4  test    rdx, rdx
0x18001ada7  cmovnz  rcx, r8
0x18001adab  mov     [rcx], r12w
0x18001adaf  jz      loc_18001AFBB
0x18001adb5  mov     r8, r15; unsigned __int16 *
0x18001adb8  mov     edx, 105h; unsigned __int64
0x18001adbd  lea     rcx, ExistingFileName; unsigned __int16 *
0x18001adc4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001adc9  mov     ebx, eax
0x18001adcb  test    eax, eax
0x18001adcd  js      loc_18001B00A
0x18001add3  mov     [rsp+50h+hTemplateFile], r12; hTemplateFile
0x18001add8  mov     [rsp+50h+dwFlagsAndAttributes], 2080h; dwFlagsAndAttributes
0x18001ade0  mov     [rsp+50h+dwCreationDisposition], 4; dwCreationDisposition
0x18001ade8  xor     r9d, r9d; lpSecurityAttributes
0x18001adeb  mov     edx, 40000000h; dwDesiredAccess
0x18001adf0  lea     r8d, [r9+5]; dwShareMode
0x18001adf4  lea     rcx, ExistingFileName; lpFileName
0x18001adfb  call    cs:__imp_CreateFileW
0x18001ae01  mov     rbx, rax
0x18001ae04  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001ae08  jnz     loc_18001ACDF
0x18001ae0e  mov     rcx, cs:hObject; hMutex
0x18001ae15  call    cs:__imp_ReleaseMutex
0x18001ae1b  call    cs:__imp_GetLastError
0x18001ae21  cmp     eax, 20h ; ' '
0x18001ae24  jnz     loc_18001AF97
0x18001ae2a  lea     ecx, [rbx+15h]; dwMilliseconds
0x18001ae2d  call    cs:__imp_Sleep
0x18001ae33  jmp     loc_18001ACDF
0x18001ae38  mov     rdx, [rbp+hObject]; void *
0x18001ae3c  test    rdx, rdx
0x18001ae3f  jz      short loc_18001AE53
0x18001ae41  call    ?DLSetThreadToken@@YAHPEAPEAXPEAX@Z; DLSetThreadToken(void * *,void *)
0x18001ae46  mov     [rbp+var_8], eax
0x18001ae49  mov     rcx, [rbp+hObject]; hObject
0x18001ae4d  call    cs:__imp_CloseHandle
0x18001ae53  mov     rax, rbx
0x18001ae56  lea     r11, [rsp+50h+var_s0]
0x18001ae5b  mov     rbx, [r11+38h]
0x18001ae5f  mov     rsi, [r11+48h]
0x18001ae63  mov     rsp, r11
0x18001ae66  pop     r15
0x18001ae68  pop     r14
0x18001ae6a  pop     r12
0x18001ae6c  pop     rdi
0x18001ae6d  pop     rbp
0x18001ae6e  retn
0x18001ae6f  cmp     qword ptr [rbp+FileSize], r14
0x18001ae73  jle     loc_18001AD30
0x18001ae79  lea     r8, ExistingFileName; unsigned __int16 *
0x18001ae80  mov     edx, 105h; unsigned __int64
0x18001ae85  lea     rcx, NewFileName; unsigned __int16 *
0x18001ae8c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001ae91  mov     esi, eax
0x18001ae93  test    eax, eax
0x18001ae95  jns     short loc_18001AEDC
0x18001ae97  mov     edx, eax; int
0x18001ae99  lea     rcx, unk_18006A9C0; this
0x18001aea0  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001aea5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aeac  lea     rax, WPP_GLOBAL_Control
0x18001aeb3  cmp     rcx, rax
0x18001aeb6  jz      short loc_18001AEDC
0x18001aeb8  test    byte ptr [rcx+1Ch], 1
0x18001aebc  jz      short loc_18001AEDC
0x18001aebe  cmp     byte ptr [rcx+19h], 2
0x18001aec2  jb      short loc_18001AEDC
0x18001aec4  mov     edx, 15h
0x18001aec9  mov     r9d, esi
0x18001aecc  lea     r8, WPP_a66c463c75c73635afca8e74831cc57c_Traceguids
0x18001aed3  mov     rcx, [rcx+10h]
0x18001aed7  call    WPP_SF_D
0x18001aedc  lea     rcx, NewFileName; lpString
0x18001aee3  call    cs:__imp_lstrlenW
0x18001aee9  movsxd  rcx, eax
0x18001aeec  lea     rax, word_18006A590
0x18001aef3  lea     rcx, [rax+rcx*2]; unsigned __int16 *
0x18001aef7  lea     r8, aLo; "lo_"
0x18001aefe  mov     edx, 105h; unsigned __int64
0x18001af03  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001af08  mov     esi, eax
0x18001af0a  test    eax, eax
0x18001af0c  jns     short loc_18001AF53
0x18001af0e  mov     edx, eax; int
0x18001af10  lea     rcx, unk_18006A9C0; this
0x18001af17  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001af1c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001af23  lea     rax, WPP_GLOBAL_Control
0x18001af2a  cmp     rcx, rax
0x18001af2d  jz      short loc_18001AF53
0x18001af2f  test    byte ptr [rcx+1Ch], 1
0x18001af33  jz      short loc_18001AF53
0x18001af35  cmp     byte ptr [rcx+19h], 2
0x18001af39  jb      short loc_18001AF53
0x18001af3b  mov     edx, 16h
0x18001af40  mov     r9d, esi
0x18001af43  lea     r8, WPP_a66c463c75c73635afca8e74831cc57c_Traceguids
0x18001af4a  mov     rcx, [rcx+10h]
0x18001af4e  call    WPP_SF_D
0x18001af53  lea     rcx, NewFileName; lpFileName
0x18001af5a  call    cs:__imp_DeleteFileW
0x18001af60  mov     r8d, 2; dwFlags
0x18001af66  lea     rdx, NewFileName; lpNewFileName
0x18001af6d  lea     rcx, ExistingFileName; lpExistingFileName
0x18001af74  call    cs:__imp_MoveFileExW
0x18001af7a  test    eax, eax
0x18001af7c  jz      loc_18001B059
0x18001af82  mov     sil, r12b
0x18001af85  mov     rcx, rbx; hObject
0x18001af88  call    cs:__imp_CloseHandle
0x18001af8e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001af92  jmp     loc_18001AD30
0x18001af97  mov     rdx, [rbp+hObject]; void *
0x18001af9b  test    rdx, rdx
0x18001af9e  jz      short loc_18001AFB2
0x18001afa0  call    ?DLSetThreadToken@@YAHPEAPEAXPEAX@Z; DLSetThreadToken(void * *,void *)
0x18001afa5  mov     [rbp+var_8], eax
0x18001afa8  mov     rcx, [rbp+hObject]; hObject
0x18001afac  call    cs:__imp_CloseHandle
0x18001afb2  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001afb6  jmp     loc_18001AE56
0x18001afbb  mov     edx, ebx; int
0x18001afbd  lea     rcx, unk_18006A9C0; this
0x18001afc4  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001afc9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001afd0  cmp     rcx, rdi
0x18001afd3  jz      loc_18001ADB5
0x18001afd9  test    byte ptr [rcx+1Ch], 1
0x18001afdd  jz      loc_18001ADB5
0x18001afe3  cmp     byte ptr [rcx+19h], 2
0x18001afe7  jb      loc_18001ADB5
0x18001afed  mov     edx, 13h
0x18001aff2  mov     r9d, ebx
0x18001aff5  lea     r8, WPP_a66c463c75c73635afca8e74831cc57c_Traceguids
0x18001affc  mov     rcx, [rcx+10h]
0x18001b000  call    WPP_SF_D
0x18001b005  jmp     loc_18001ADB5
0x18001b00a  mov     edx, ebx; int
0x18001b00c  lea     rcx, unk_18006A9C0; this
0x18001b013  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001b018  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b01f  cmp     rcx, rdi
0x18001b022  jz      loc_18001ADD3
0x18001b028  test    byte ptr [rcx+1Ch], 1
0x18001b02c  jz      loc_18001ADD3
0x18001b032  cmp     byte ptr [rcx+19h], 2
0x18001b036  jb      loc_18001ADD3
0x18001b03c  mov     edx, 14h
0x18001b041  mov     r9d, ebx
0x18001b044  lea     r8, WPP_a66c463c75c73635afca8e74831cc57c_Traceguids
0x18001b04b  mov     rcx, [rcx+10h]
0x18001b04f  call    WPP_SF_D
0x18001b054  jmp     loc_18001ADD3
0x18001b059  lea     rax, [r14+r14]
0x18001b05d  cmp     qword ptr [rbp+FileSize], rax
0x18001b061  jge     short loc_18001B071
0x18001b063  mov     rcx, rdi; hMutex
0x18001b066  call    cs:__imp_ReleaseMutex
0x18001b06c  jmp     loc_18001AE38
0x18001b071  mov     rcx, rbx; hObject
0x18001b074  call    cs:__imp_CloseHandle
0x18001b07a  nop
0x18001b07b  mov     rcx, rdi; hMutex
0x18001b07e  call    cs:__imp_ReleaseMutex
0x18001b084  jmp     loc_18001AF97
```
