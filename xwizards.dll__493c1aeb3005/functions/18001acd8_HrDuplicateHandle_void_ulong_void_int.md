# HrDuplicateHandle(void *,ulong,void * *,int)

- ea: `0x18001acd8`
- end: `0x18001af5d`
- name: `?HrDuplicateHandle@@YAJPEAXKPEAPEAXH@Z`
- size: `645`
- prototype: `__int64 __fastcall(HANDLE hSourceHandle, DWORD dwProcessId, void **, int)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18001abe4`
- `0x18001b080`
- `0x18001b1d0`
- `0x18001b434`

## callees

- `0x180004370`
- `0x18000ae04`
- `0x18000ae44`
- `0x18001acd8`
- `0x18001b864`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001ada2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001ae25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001ada2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001ae25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001ad5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001adf0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001ae86`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001ad5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001adf0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001ae86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ae65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001aeaf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001af11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ae65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001aeaf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001af11`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001adcd`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001ae4e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001adcd`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001ae4e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001ad70`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001ad70`

## pseudocode

```c
__int64 __fastcall HrDuplicateHandle(HANDLE hSourceHandle, DWORD dwProcessId, void **a3, int a4)
{
  DWORD CurrentProcessId; // esi
  HANDLE v9; // r12
  int LastErrorHRESULT; // ebx
  DWORD dwOptions; // r15d
  HANDLE CurrentProcess; // rax
  DWORD v13; // eax
  __int64 v14; // r8
  HANDLE v15; // rax
  DWORD v16; // eax
  __int64 v17; // r8
  int v18; // eax
  PVOID *v19; // rcx
  HANDLE hObject; // [rsp+40h] [rbp-38h] BYREF
  HANDLE TargetHandle; // [rsp+90h] [rbp+18h] BYREF

  hObject = 0;
  CurrentProcessId = dwProcessId;
  if ( a3 )
  {
    *a3 = 0;
  }
  else if ( !a4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_57b06483306a3a4d34d88419a088456d_Traceguids, 2147942487LL);
    return 2147942487LL;
  }
  if ( !hSourceHandle )
    return 1;
  if ( !dwProcessId )
    CurrentProcessId = GetCurrentProcessId();
  v9 = OpenProcess(0x40u, 1, CurrentProcessId);
  if ( v9 )
  {
    TargetHandle = 0;
    LastErrorHRESULT = 0;
    if ( a4 )
    {
      dwOptions = 3;
      CurrentProcess = GetCurrentProcess();
      if ( !DuplicateHandle(v9, hSourceHandle, CurrentProcess, &TargetHandle, 0, 1, 2u) )
      {
        LastErrorHRESULT = GetLastErrorHRESULT();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v13 = GetCurrentProcessId();
          WPP_SF_DDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, v14, CurrentProcessId, v13, LastErrorHRESULT);
        }
        if ( LastErrorHRESULT < 0 )
          goto LABEL_27;
      }
    }
    else
    {
      dwOptions = 2;
    }
    v15 = GetCurrentProcess();
    if ( DuplicateHandle(v9, hSourceHandle, v15, &hObject, 0, 1, dwOptions) )
    {
      if ( TargetHandle )
        CloseHandle(TargetHandle);
    }
    else
    {
      LastErrorHRESULT = GetLastErrorHRESULT();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v16 = GetCurrentProcessId();
        WPP_SF_DDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, v17, CurrentProcessId, v16, LastErrorHRESULT);
      }
    }
LABEL_27:
    CloseHandle(v9);
    goto LABEL_31;
  }
  v18 = GetLastErrorHRESULT();
  LastErrorHRESULT = v18;
  v19 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    goto LABEL_32;
  WPP_SF_DD(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    26,
    &WPP_57b06483306a3a4d34d88419a088456d_Traceguids,
    CurrentProcessId,
    v18);
LABEL_31:
  v19 = (PVOID *)WPP_GLOBAL_Control;
LABEL_32:
  if ( hObject )
  {
    if ( a3 )
      *a3 = hObject;
    else
      CloseHandle(hObject);
    v19 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 0x10) != 0 )
    WPP_SF_d(v19[2], 27, &WPP_57b06483306a3a4d34d88419a088456d_Traceguids, (unsigned int)LastErrorHRESULT);
  return (unsigned int)LastErrorHRESULT;
}

```

## disassembly

```asm
0x18001acd8  mov     [rsp+arg_0], rbx
0x18001acdd  mov     [rsp+arg_8], rsi
0x18001ace2  push    rdi
0x18001ace3  push    r12
0x18001ace5  push    r13
0x18001ace7  push    r14
0x18001ace9  push    r15
0x18001aceb  sub     rsp, 50h
0x18001acef  xor     edi, edi
0x18001acf1  mov     r15d, r9d
0x18001acf4  mov     [rsp+78h+hObject], rdi
0x18001acf9  mov     r14, r8
0x18001acfc  mov     esi, edx
0x18001acfe  mov     r13, rcx
0x18001ad01  test    r8, r8
0x18001ad04  jnz     short loc_18001AD48
0x18001ad06  test    r9d, r9d
0x18001ad09  jnz     short loc_18001AD4B
0x18001ad0b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ad12  lea     rdi, WPP_GLOBAL_Control
0x18001ad19  cmp     rcx, rdi
0x18001ad1c  jz      short loc_18001AD3E
0x18001ad1e  test    byte ptr [rcx+1Ch], 4
0x18001ad22  jz      short loc_18001AD3E
0x18001ad24  mov     rcx, [rcx+10h]
0x18001ad28  lea     edx, [r9+17h]
0x18001ad2c  mov     r9d, 80070057h
0x18001ad32  lea     r8, WPP_57b06483306a3a4d34d88419a088456d_Traceguids
0x18001ad39  call    WPP_SF_d
0x18001ad3e  mov     eax, 80070057h
0x18001ad43  jmp     loc_18001AF43
0x18001ad48  mov     [r8], rdi
0x18001ad4b  test    r13, r13
0x18001ad4e  jnz     short loc_18001AD59
0x18001ad50  lea     eax, [r13+1]
0x18001ad54  jmp     loc_18001AF43
0x18001ad59  test    edx, edx
0x18001ad5b  jnz     short loc_18001AD65
0x18001ad5d  call    cs:__imp_GetCurrentProcessId
0x18001ad63  mov     esi, eax
0x18001ad65  mov     edx, 1; bInheritHandle
0x18001ad6a  mov     r8d, esi; dwProcessId
0x18001ad6d  lea     ecx, [rdx+3Fh]; dwDesiredAccess
0x18001ad70  call    cs:__imp_OpenProcess
0x18001ad76  mov     r12, rax
0x18001ad79  test    rax, rax
0x18001ad7c  jz      loc_18001AEB7
0x18001ad82  mov     [rsp+78h+TargetHandle], rdi
0x18001ad8a  mov     ebx, edi
0x18001ad8c  lea     rdi, WPP_GLOBAL_Control
0x18001ad93  test    r15d, r15d
0x18001ad96  jz      loc_18001AE1F
0x18001ad9c  mov     r15d, 3
0x18001ada2  call    cs:__imp_GetCurrentProcess
0x18001ada8  mov     [rsp+78h+dwOptions], 2; dwOptions
0x18001adb0  lea     r9, [rsp+78h+TargetHandle]; lpTargetHandle
0x18001adb8  mov     r8, rax; hTargetProcessHandle
0x18001adbb  mov     [rsp+78h+bInheritHandle], 1; bInheritHandle
0x18001adc3  mov     rdx, r13; hSourceHandle
0x18001adc6  mov     [rsp+78h+dwDesiredAccess], ebx; dwDesiredAccess
0x18001adca  mov     rcx, r12; hSourceProcessHandle
0x18001adcd  call    cs:__imp_DuplicateHandle
0x18001add3  test    eax, eax
0x18001add5  jnz     short loc_18001AE25
0x18001add7  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18001addc  mov     ebx, eax
0x18001adde  mov     rax, cs:WPP_GLOBAL_Control
0x18001ade5  cmp     rax, rdi
0x18001ade8  jz      short loc_18001AE15
0x18001adea  test    byte ptr [rax+1Ch], 4
0x18001adee  jz      short loc_18001AE15
0x18001adf0  call    cs:__imp_GetCurrentProcessId
0x18001adf6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001adfd  lea     edx, [r15+15h]
0x18001ae01  mov     [rsp+78h+bInheritHandle], ebx
0x18001ae05  mov     r9d, esi
0x18001ae08  mov     [rsp+78h+dwDesiredAccess], eax
0x18001ae0c  mov     rcx, [rcx+10h]
0x18001ae10  call    WPP_SF_DDD
0x18001ae15  test    ebx, ebx
0x18001ae17  js      loc_18001AEAC
0x18001ae1d  jmp     short loc_18001AE25
0x18001ae1f  mov     r15d, 2
0x18001ae25  call    cs:__imp_GetCurrentProcess
0x18001ae2b  mov     [rsp+78h+dwOptions], r15d; dwOptions
0x18001ae30  lea     r9, [rsp+78h+hObject]; lpTargetHandle
0x18001ae35  mov     r8, rax; hTargetProcessHandle
0x18001ae38  mov     [rsp+78h+bInheritHandle], 1; bInheritHandle
0x18001ae40  mov     rdx, r13; hSourceHandle
0x18001ae43  mov     [rsp+78h+dwDesiredAccess], 0; dwDesiredAccess
0x18001ae4b  mov     rcx, r12; hSourceProcessHandle
0x18001ae4e  call    cs:__imp_DuplicateHandle
0x18001ae54  test    eax, eax
0x18001ae56  jz      short loc_18001AE6D
0x18001ae58  mov     rcx, [rsp+78h+TargetHandle]; hObject
0x18001ae60  test    rcx, rcx
0x18001ae63  jz      short loc_18001AEAC
0x18001ae65  call    cs:__imp_CloseHandle
0x18001ae6b  jmp     short loc_18001AEAC
0x18001ae6d  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18001ae72  mov     ebx, eax
0x18001ae74  mov     rax, cs:WPP_GLOBAL_Control
0x18001ae7b  cmp     rax, rdi
0x18001ae7e  jz      short loc_18001AEAC
0x18001ae80  test    byte ptr [rax+1Ch], 4
0x18001ae84  jz      short loc_18001AEAC
0x18001ae86  call    cs:__imp_GetCurrentProcessId
0x18001ae8c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ae93  mov     edx, 19h
0x18001ae98  mov     [rsp+78h+bInheritHandle], ebx
0x18001ae9c  mov     r9d, esi
0x18001ae9f  mov     [rsp+78h+dwDesiredAccess], eax
0x18001aea3  mov     rcx, [rcx+10h]
0x18001aea7  call    WPP_SF_DDD
0x18001aeac  mov     rcx, r12; hObject
0x18001aeaf  call    cs:__imp_CloseHandle
0x18001aeb5  jmp     short loc_18001AEF3
0x18001aeb7  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18001aebc  mov     ebx, eax
0x18001aebe  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aec5  lea     rdi, WPP_GLOBAL_Control
0x18001aecc  cmp     rcx, rdi
0x18001aecf  jz      short loc_18001AEFA
0x18001aed1  test    byte ptr [rcx+1Ch], 4
0x18001aed5  jz      short loc_18001AEFA
0x18001aed7  mov     rcx, [rcx+10h]
0x18001aedb  lea     r8, WPP_57b06483306a3a4d34d88419a088456d_Traceguids
0x18001aee2  mov     edx, 1Ah
0x18001aee7  mov     [rsp+78h+dwDesiredAccess], eax
0x18001aeeb  mov     r9d, esi
0x18001aeee  call    WPP_SF_DD
0x18001aef3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aefa  mov     rax, [rsp+78h+hObject]
0x18001aeff  test    rax, rax
0x18001af02  jz      short loc_18001AF1E
0x18001af04  test    r14, r14
0x18001af07  jz      short loc_18001AF0E
0x18001af09  mov     [r14], rax
0x18001af0c  jmp     short loc_18001AF17
0x18001af0e  mov     rcx, rax; hObject
0x18001af11  call    cs:__imp_CloseHandle
0x18001af17  mov     rcx, cs:WPP_GLOBAL_Control
0x18001af1e  cmp     rcx, rdi
0x18001af21  jz      short loc_18001AF41
0x18001af23  test    byte ptr [rcx+1Ch], 10h
0x18001af27  jz      short loc_18001AF41
0x18001af29  mov     rcx, [rcx+10h]
0x18001af2d  lea     r8, WPP_57b06483306a3a4d34d88419a088456d_Traceguids
0x18001af34  mov     edx, 1Bh
0x18001af39  mov     r9d, ebx
0x18001af3c  call    WPP_SF_d
0x18001af41  mov     eax, ebx
0x18001af43  lea     r11, [rsp+78h+var_28]
0x18001af48  mov     rbx, [r11+30h]
0x18001af4c  mov     rsi, [r11+38h]
0x18001af50  mov     rsp, r11
0x18001af53  pop     r15
0x18001af55  pop     r14
0x18001af57  pop     r13
0x18001af59  pop     r12
0x18001af5b  pop     rdi
0x18001af5c  retn
```
