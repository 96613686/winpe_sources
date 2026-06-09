# WlRemindersTerminateWorkerCallback(_TP_CALLBACK_INSTANCE *,void *)

- ea: `0x140077e90`
- end: `0x140078131`
- name: `?WlRemindersTerminateWorkerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z`
- size: `673`
- prototype: `void(struct _TP_CALLBACK_INSTANCE *, void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x14000d4e0`
- `0x140053720`
- `0x14005fb84`
- `0x140077e90`
- `0x140078740`
- `0x14007896c`
- `0x1400789c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140077f3d`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140077f3d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140077faa`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140077faa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140078010`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140078010`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140077ef1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140077f76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140077fdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400780b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140077ef1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140077f76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140077fdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400780b8`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140077ebc`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140077ebc`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140078096`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x140078096`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140078084`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14007810f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140078084`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14007810f`

## pseudocode

```c
void __fastcall WlRemindersTerminateWorkerCallback(struct _TP_CALLBACK_INSTANCE *a1, void *a2)
{
  DWORD ProcessId; // eax
  DWORD LastError; // eax
  __int64 v5; // r8
  HANDLE v6; // rax
  void *v7; // rbp
  char v8; // al
  int v9; // r8d
  int v10; // esi
  char v11; // al
  int v12; // r8d
  CUser *v13; // rcx
  int v14; // edx
  DWORD v15; // eax
  __int64 v16; // r8
  WCHAR Name[264]; // [rsp+30h] [rbp-248h] BYREF

  if ( a2 )
  {
    ProcessId = GetProcessId(a2);
    if ( !ProcessId )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, v5, a2, LastError);
      }
      goto LABEL_28;
    }
    StringCchPrintfW(Name, 0x104u, L"Local\\Wl_Stop_Reminder_Event_%ld", ProcessId);
    v6 = OpenEventW(0x1F0003u, 0, Name);
    v7 = v6;
    if ( !v6 )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v8 = GetLastError();
        WPP_SF_SqD(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, v9, (unsigned int)Name, (char)a2, v8);
      }
      goto LABEL_28;
    }
    v10 = 1;
    if ( !SetEvent(v6) )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = GetLastError();
        WPP_SF_SqD(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, v12, (unsigned int)Name, (char)a2, v11);
      }
LABEL_27:
      CloseHandle(v7);
      if ( !v10 )
      {
LABEL_37:
        CloseHandle(a2);
        return;
      }
LABEL_28:
      if ( TerminateProcess(a2, 0x3E3u) )
      {
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_45f944bba9fd33a68794881c2280ffd4_Traceguids, a2);
        }
      }
      else if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = GetLastError();
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, v16, a2, v15);
      }
      goto LABEL_37;
    }
    if ( WaitForSingleObject(a2, 0x1388u) )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_27;
      }
      v14 = 23;
    }
    else
    {
      v10 = 0;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_27;
      }
      v14 = 24;
    }
    WPP_SF_qS(
      *((_QWORD *)v13 + 2),
      v14,
      (unsigned int)WPP_45f944bba9fd33a68794881c2280ffd4_Traceguids,
      (_DWORD)a2,
      (__int64)Name);
    goto LABEL_27;
  }
}

```

## disassembly

```asm
0x140077e90  test    rdx, rdx
0x140077e93  jz      locret_140078130
0x140077e99  push    rbx
0x140077e9a  push    rbp
0x140077e9b  push    rsi
0x140077e9c  push    rdi
0x140077e9d  sub     rsp, 258h
0x140077ea4  mov     rax, cs:__security_cookie
0x140077eab  xor     rax, rsp
0x140077eae  mov     [rsp+278h+var_38], rax
0x140077eb6  mov     rcx, rdx; Process
0x140077eb9  mov     rbx, rdx
0x140077ebc  call    cs:__imp_GetProcessId
0x140077ec2  test    eax, eax
0x140077ec4  jnz     short loc_140077F18
0x140077ec6  mov     rax, cs:WPP_GLOBAL_Control
0x140077ecd  lea     rdi, WPP_GLOBAL_Control
0x140077ed4  cmp     rax, rdi
0x140077ed7  jz      loc_14007808E
0x140077edd  test    byte ptr [rax+1Ch], 20h
0x140077ee1  jz      loc_14007808E
0x140077ee7  cmp     byte ptr [rax+19h], 2
0x140077eeb  jb      loc_14007808E
0x140077ef1  call    cs:__imp_GetLastError
0x140077ef7  mov     rcx, cs:WPP_GLOBAL_Control
0x140077efe  mov     edx, 14h
0x140077f03  mov     r9, rbx
0x140077f06  mov     dword ptr [rsp+278h+var_258], eax
0x140077f0a  mov     rcx, [rcx+10h]
0x140077f0e  call    WPP_SF_qD
0x140077f13  jmp     loc_14007808E
0x140077f18  mov     r9d, eax
0x140077f1b  lea     r8, aLocalWlStopRem; "Local\\Wl_Stop_Reminder_Event_%ld"
0x140077f22  mov     edx, 104h; unsigned __int64
0x140077f27  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x140077f2c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140077f31  lea     r8, [rsp+278h+Name]; lpName
0x140077f36  xor     edx, edx; bInheritHandle
0x140077f38  mov     ecx, 1F0003h; dwDesiredAccess
0x140077f3d  call    cs:__imp_OpenEventW
0x140077f43  mov     rbp, rax
0x140077f46  test    rax, rax
0x140077f49  jnz     short loc_140077FA2
0x140077f4b  mov     rax, cs:WPP_GLOBAL_Control
0x140077f52  lea     rdi, WPP_GLOBAL_Control
0x140077f59  cmp     rax, rdi
0x140077f5c  jz      loc_14007808E
0x140077f62  test    byte ptr [rax+1Ch], 20h
0x140077f66  jz      loc_14007808E
0x140077f6c  cmp     byte ptr [rax+19h], 2
0x140077f70  jb      loc_14007808E
0x140077f76  call    cs:__imp_GetLastError
0x140077f7c  mov     rcx, cs:WPP_GLOBAL_Control
0x140077f83  lea     edx, [rbp+15h]
0x140077f86  mov     [rsp+278h+var_250], eax
0x140077f8a  lea     r9, [rsp+278h+Name]
0x140077f8f  mov     [rsp+278h+var_258], rbx
0x140077f94  mov     rcx, [rcx+10h]
0x140077f98  call    WPP_SF_SqD
0x140077f9d  jmp     loc_14007808E
0x140077fa2  mov     rcx, rbp; hEvent
0x140077fa5  mov     esi, 1
0x140077faa  call    cs:__imp_SetEvent
0x140077fb0  test    eax, eax
0x140077fb2  jnz     short loc_140078008
0x140077fb4  mov     rax, cs:WPP_GLOBAL_Control
0x140077fbb  lea     rdi, WPP_GLOBAL_Control
0x140077fc2  cmp     rax, rdi
0x140077fc5  jz      loc_140078081
0x140077fcb  test    byte ptr [rax+1Ch], 20h
0x140077fcf  jz      loc_140078081
0x140077fd5  cmp     byte ptr [rax+19h], 2
0x140077fd9  jb      loc_140078081
0x140077fdf  call    cs:__imp_GetLastError
0x140077fe5  mov     rcx, cs:WPP_GLOBAL_Control
0x140077fec  lea     edx, [rsi+15h]
0x140077fef  mov     [rsp+278h+var_250], eax
0x140077ff3  lea     r9, [rsp+278h+Name]
0x140077ff8  mov     [rsp+278h+var_258], rbx
0x140077ffd  mov     rcx, [rcx+10h]
0x140078001  call    WPP_SF_SqD
0x140078006  jmp     short loc_140078081
0x140078008  mov     edx, 1388h; dwMilliseconds
0x14007800d  mov     rcx, rbx; hHandle
0x140078010  call    cs:__imp_WaitForSingleObject
0x140078016  test    eax, eax
0x140078018  jz      short loc_140078040
0x14007801a  mov     rcx, cs:WPP_GLOBAL_Control
0x140078021  lea     rdi, WPP_GLOBAL_Control
0x140078028  cmp     rcx, rdi
0x14007802b  jz      short loc_140078081
0x14007802d  test    byte ptr [rcx+1Ch], 20h
0x140078031  jz      short loc_140078081
0x140078033  cmp     byte ptr [rcx+19h], 2
0x140078037  jb      short loc_140078081
0x140078039  mov     edx, 17h
0x14007803e  jmp     short loc_140078064
0x140078040  xor     esi, esi
0x140078042  mov     rcx, cs:WPP_GLOBAL_Control
0x140078049  lea     rdi, WPP_GLOBAL_Control
0x140078050  cmp     rcx, rdi
0x140078053  jz      short loc_140078081
0x140078055  test    byte ptr [rcx+1Ch], 20h
0x140078059  jz      short loc_140078081
0x14007805b  cmp     byte ptr [rcx+19h], 4
0x14007805f  jb      short loc_140078081
0x140078061  lea     edx, [rsi+18h]
0x140078064  mov     rcx, [rcx+10h]
0x140078068  lea     rax, [rsp+278h+Name]
0x14007806d  mov     r9, rbx
0x140078070  mov     [rsp+278h+var_258], rax
0x140078075  lea     r8, WPP_45f944bba9fd33a68794881c2280ffd4_Traceguids
0x14007807c  call    WPP_SF_qS
0x140078081  mov     rcx, rbp; hObject
0x140078084  call    cs:__imp_CloseHandle
0x14007808a  test    esi, esi
0x14007808c  jz      short loc_14007810C
0x14007808e  mov     edx, 3E3h; uExitCode
0x140078093  mov     rcx, rbx; hProcess
0x140078096  call    cs:__imp_TerminateProcess
0x14007809c  test    eax, eax
0x14007809e  jnz     short loc_1400780DC
0x1400780a0  mov     rax, cs:WPP_GLOBAL_Control
0x1400780a7  cmp     rax, rdi
0x1400780aa  jz      short loc_14007810C
0x1400780ac  test    byte ptr [rax+1Ch], 20h
0x1400780b0  jz      short loc_14007810C
0x1400780b2  cmp     byte ptr [rax+19h], 2
0x1400780b6  jb      short loc_14007810C
0x1400780b8  call    cs:__imp_GetLastError
0x1400780be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400780c5  mov     edx, 19h
0x1400780ca  mov     r9, rbx
0x1400780cd  mov     dword ptr [rsp+278h+var_258], eax
0x1400780d1  mov     rcx, [rcx+10h]
0x1400780d5  call    WPP_SF_qD
0x1400780da  jmp     short loc_14007810C
0x1400780dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400780e3  cmp     rcx, rdi
0x1400780e6  jz      short loc_14007810C
0x1400780e8  test    byte ptr [rcx+1Ch], 20h
0x1400780ec  jz      short loc_14007810C
0x1400780ee  cmp     byte ptr [rcx+19h], 4
0x1400780f2  jb      short loc_14007810C
0x1400780f4  mov     rcx, [rcx+10h]
0x1400780f8  lea     r8, WPP_45f944bba9fd33a68794881c2280ffd4_Traceguids
0x1400780ff  mov     edx, 1Ah
0x140078104  mov     r9, rbx
0x140078107  call    WPP_SF_q
0x14007810c  mov     rcx, rbx; hObject
0x14007810f  call    cs:__imp_CloseHandle
0x140078115  mov     rcx, [rsp+278h+var_38]
0x14007811d  xor     rcx, rsp; StackCookie
0x140078120  call    __security_check_cookie
0x140078125  add     rsp, 258h
0x14007812c  pop     rdi
0x14007812d  pop     rsi
0x14007812e  pop     rbp
0x14007812f  pop     rbx
0x140078130  retn
```
