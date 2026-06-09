# GetCreateProcessToken(void *,ulong,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x18002060c`
- end: `0x180020913`
- name: `?GetCreateProcessToken@@YAJPEAXKPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `775`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18001fb94`

## callees

- `0x180006a80`
- `0x180011ef8`
- `0x18002060c`
- `0x1800243ac`
- `0x18002ff0c`
- `0x1800300c0`
- `0x180030590`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800206db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800206db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800207d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800207f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020810`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800208e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800208f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800207d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800207f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020810`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800208e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800208f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetCreateProcessToken(HANDLE ProcessHandle, __int64 a2, void **a3)
{
  int ProcessToken; // ebx
  int ActiveSessionToken; // eax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  HANDLE CurrentProcess; // rax
  HANDLE v10; // rbx
  HANDLE v11; // rcx
  void *v12; // rcx
  HANDLE hExistingToken; // [rsp+40h] [rbp+20h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp+38h] BYREF

  hExistingToken = 0;
  if ( !ProcessHandle && (a2 & 0x100) == 0 || !a3 )
  {
    ProcessToken = -2147024809;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids);
    goto LABEL_52;
  }
  if ( (a2 & 0x100) != 0 )
  {
    ActiveSessionToken = UserTokenUtility::GetActiveSessionToken((__int64)ProcessHandle, a2, &hExistingToken);
    ProcessToken = ActiveSessionToken;
    if ( ActiveSessionToken != -2147024846 && ActiveSessionToken != -2147023888 )
    {
      if ( ActiveSessionToken < 0 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_52;
        v8 = 12;
        goto LABEL_18;
      }
      goto LABEL_48;
    }
    CurrentProcess = GetCurrentProcess();
    ProcessToken = UserTokenUtility::GetProcessToken(CurrentProcess, 1, &hExistingToken);
    if ( ProcessToken < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_52;
      v8 = 11;
      goto LABEL_18;
    }
LABEL_48:
    v10 = hExistingToken;
LABEL_49:
    hExistingToken = 0;
    v12 = *a3;
    *a3 = v10;
    if ( (unsigned __int64)v12 + 1 > 1 )
      CloseHandle(v12);
    ProcessToken = 0;
    goto LABEL_52;
  }
  if ( (a2 & 4) == 0 )
  {
    if ( (a2 & 8) != 0 )
    {
      ProcessToken = UserTokenUtility::GetUserToken(ProcessHandle, a2, &hExistingToken);
      if ( ProcessToken == -2147024846 )
      {
        ProcessToken = UserTokenUtility::GetProcessToken(ProcessHandle, 0, &hExistingToken);
        if ( ProcessToken >= 0 )
          goto LABEL_48;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_52;
        v8 = 15;
      }
      else
      {
        if ( ProcessToken >= 0 )
          goto LABEL_48;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_52;
        v8 = 16;
      }
    }
    else
    {
      ProcessToken = UserTokenUtility::GetProcessToken(ProcessHandle, 0, &hExistingToken);
      if ( ProcessToken >= 0 )
        goto LABEL_48;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_52;
      v8 = 17;
    }
LABEL_18:
    WPP_SF_d(v7[2], v8, &WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids, (unsigned int)ProcessToken);
    goto LABEL_52;
  }
  ProcessToken = UserTokenUtility::GetProcessToken(ProcessHandle, 1, &hExistingToken);
  if ( ProcessToken < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_52;
    v8 = 13;
    goto LABEL_18;
  }
  hObject = 0;
  ProcessToken = UtilTokenGiveUIAccess(hExistingToken, &hObject);
  if ( ProcessToken >= 0 )
  {
    v10 = hObject;
    v11 = 0;
    hObject = 0;
    if ( (unsigned __int64)hExistingToken + 1 > 1 )
    {
      CloseHandle(hExistingToken);
      v11 = hObject;
    }
    if ( (unsigned __int64)v11 + 1 > 1 )
      CloseHandle(v11);
    goto LABEL_49;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      &WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids,
      (unsigned int)ProcessToken);
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
LABEL_52:
  if ( (unsigned __int64)hExistingToken + 1 > 1 )
    CloseHandle(hExistingToken);
  return (unsigned int)ProcessToken;
}

```

## disassembly

```asm
0x18002060c  mov     [rsp-18h+arg_8], rbx
0x180020611  mov     [rsp-18h+arg_10], rsi
0x180020616  push    rbp
0x180020617  push    rdi
0x180020618  push    r14
0x18002061a  mov     rbp, rsp
0x18002061d  sub     rsp, 20h
0x180020621  mov     rsi, r8
0x180020624  mov     rdi, rcx
0x180020627  mov     [rbp+hExistingToken], 0
0x18002062f  mov     eax, edx
0x180020631  and     eax, 100h
0x180020636  mov     r14d, 1
0x18002063c  test    rcx, rcx
0x18002063f  jnz     short loc_180020645
0x180020641  test    eax, eax
0x180020643  jz      short loc_18002064A
0x180020645  test    rsi, rsi
0x180020648  jnz     short loc_18002068A
0x18002064a  mov     ebx, 80070057h
0x18002064f  lea     rax, WPP_GLOBAL_Control
0x180020656  mov     rcx, cs:WPP_GLOBAL_Control
0x18002065d  cmp     rcx, rax
0x180020660  jz      loc_1800208EB
0x180020666  test    [rcx+1Ch], r14b
0x18002066a  jz      loc_1800208EB
0x180020670  mov     edx, 0Ah
0x180020675  lea     r8, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids
0x18002067c  mov     rcx, [rcx+10h]
0x180020680  call    WPP_SF_
0x180020685  jmp     loc_1800208EB
0x18002068a  lea     r8, [rbp+hExistingToken]
0x18002068e  test    eax, eax
0x180020690  jz      loc_180020738
0x180020696  call    ?GetActiveSessionToken@UserTokenUtility@@SAJHHPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; UserTokenUtility::GetActiveSessionToken(int,int,tlx::unique_any<tlx::file_handle_traits> *)
0x18002069b  mov     ebx, eax
0x18002069d  cmp     eax, 80070032h
0x1800206a2  jz      short loc_1800206DB
0x1800206a4  cmp     eax, 800703F0h
0x1800206a9  jz      short loc_1800206DB
0x1800206ab  test    eax, eax
0x1800206ad  jns     loc_1800208C8
0x1800206b3  lea     rax, WPP_GLOBAL_Control
0x1800206ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800206c1  cmp     rcx, rax
0x1800206c4  jz      loc_1800208EB
0x1800206ca  test    [rcx+1Ch], r14b
0x1800206ce  jz      loc_1800208EB
0x1800206d4  mov     edx, 0Ch
0x1800206d9  jmp     short loc_180020720
0x1800206db  call    cs:__imp_GetCurrentProcess
0x1800206e1  mov     rcx, rax; ProcessHandle
0x1800206e4  lea     r8, [rbp+hExistingToken]
0x1800206e8  mov     edx, r14d
0x1800206eb  call    ?GetProcessToken@UserTokenUtility@@SAJPEAXHPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; UserTokenUtility::GetProcessToken(void *,int,tlx::unique_any<tlx::file_handle_traits> *)
0x1800206f0  mov     ebx, eax
0x1800206f2  test    eax, eax
0x1800206f4  jns     loc_1800208C8
0x1800206fa  lea     rax, WPP_GLOBAL_Control
0x180020701  mov     rcx, cs:WPP_GLOBAL_Control
0x180020708  cmp     rcx, rax
0x18002070b  jz      loc_1800208EB
0x180020711  test    [rcx+1Ch], r14b
0x180020715  jz      loc_1800208EB
0x18002071b  mov     edx, 0Bh
0x180020720  mov     r9d, ebx
0x180020723  lea     r8, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids
0x18002072a  mov     rcx, [rcx+10h]
0x18002072e  call    WPP_SF_d
0x180020733  jmp     loc_1800208EB
0x180020738  test    dl, 4
0x18002073b  jz      loc_18002081B
0x180020741  mov     edx, r14d
0x180020744  call    ?GetProcessToken@UserTokenUtility@@SAJPEAXHPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; UserTokenUtility::GetProcessToken(void *,int,tlx::unique_any<tlx::file_handle_traits> *)
0x180020749  mov     ebx, eax
0x18002074b  test    eax, eax
0x18002074d  jns     short loc_180020777
0x18002074f  lea     rax, WPP_GLOBAL_Control
0x180020756  mov     rcx, cs:WPP_GLOBAL_Control
0x18002075d  cmp     rcx, rax
0x180020760  jz      loc_1800208EB
0x180020766  test    [rcx+1Ch], r14b
0x18002076a  jz      loc_1800208EB
0x180020770  mov     edx, 0Dh
0x180020775  jmp     short loc_180020720
0x180020777  mov     [rbp+hObject], 0
0x18002077f  lea     rdx, [rbp+hObject]
0x180020783  mov     rcx, [rbp+hExistingToken]; hExistingToken
0x180020787  call    UtilTokenGiveUIAccess
0x18002078c  mov     ebx, eax
0x18002078e  test    eax, eax
0x180020790  jns     short loc_1800207DF
0x180020792  lea     rax, WPP_GLOBAL_Control
0x180020799  mov     rcx, cs:WPP_GLOBAL_Control
0x1800207a0  cmp     rcx, rax
0x1800207a3  jz      short loc_1800207C3
0x1800207a5  test    [rcx+1Ch], r14b
0x1800207a9  jz      short loc_1800207C3
0x1800207ab  mov     edx, 0Eh
0x1800207b0  mov     r9d, ebx
0x1800207b3  lea     r8, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids
0x1800207ba  mov     rcx, [rcx+10h]
0x1800207be  call    WPP_SF_d
0x1800207c3  mov     rcx, [rbp+hObject]; hObject
0x1800207c7  lea     rax, [rcx+1]
0x1800207cb  cmp     rax, r14
0x1800207ce  jbe     loc_1800208EB
0x1800207d4  call    cs:__imp_CloseHandle
0x1800207da  jmp     loc_1800208EB
0x1800207df  mov     rbx, [rbp+hObject]
0x1800207e3  xor     ecx, ecx
0x1800207e5  mov     [rbp+hObject], rcx
0x1800207e9  mov     rdx, [rbp+hExistingToken]
0x1800207ed  lea     rax, [rdx+1]
0x1800207f1  cmp     rax, r14
0x1800207f4  jbe     short loc_180020803
0x1800207f6  mov     rcx, rdx; hObject
0x1800207f9  call    cs:__imp_CloseHandle
0x1800207ff  mov     rcx, [rbp+hObject]; hObject
0x180020803  lea     rax, [rcx+1]
0x180020807  cmp     rax, r14
0x18002080a  jbe     loc_1800208CC
0x180020810  call    cs:__imp_CloseHandle
0x180020816  jmp     loc_1800208CC
0x18002081b  test    dl, 8
0x18002081e  jz      short loc_180020898
0x180020820  call    ?GetUserToken@UserTokenUtility@@SAJPEAXHPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; UserTokenUtility::GetUserToken(void *,int,tlx::unique_any<tlx::file_handle_traits> *)
0x180020825  mov     ebx, eax
0x180020827  cmp     eax, 80070032h
0x18002082c  jnz     short loc_180020871
0x18002082e  lea     r8, [rbp+hExistingToken]
0x180020832  xor     edx, edx
0x180020834  mov     rcx, rdi; ProcessHandle
0x180020837  call    ?GetProcessToken@UserTokenUtility@@SAJPEAXHPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; UserTokenUtility::GetProcessToken(void *,int,tlx::unique_any<tlx::file_handle_traits> *)
0x18002083c  mov     ebx, eax
0x18002083e  test    eax, eax
0x180020840  jns     loc_1800208C8
0x180020846  lea     rax, WPP_GLOBAL_Control
0x18002084d  mov     rcx, cs:WPP_GLOBAL_Control
0x180020854  cmp     rcx, rax
0x180020857  jz      loc_1800208EB
0x18002085d  test    [rcx+1Ch], r14b
0x180020861  jz      loc_1800208EB
0x180020867  mov     edx, 0Fh
0x18002086c  jmp     loc_180020720
0x180020871  test    ebx, ebx
0x180020873  jns     short loc_1800208C8
0x180020875  lea     rax, WPP_GLOBAL_Control
0x18002087c  mov     rcx, cs:WPP_GLOBAL_Control; ProcessHandle
0x180020883  cmp     rcx, rax
0x180020886  jz      short loc_1800208EB
0x180020888  test    [rcx+1Ch], r14b
0x18002088c  jz      short loc_1800208EB
0x18002088e  mov     edx, 10h
0x180020893  jmp     loc_180020720
0x180020898  xor     edx, edx
0x18002089a  call    ?GetProcessToken@UserTokenUtility@@SAJPEAXHPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; UserTokenUtility::GetProcessToken(void *,int,tlx::unique_any<tlx::file_handle_traits> *)
0x18002089f  mov     ebx, eax
0x1800208a1  test    eax, eax
0x1800208a3  jns     short loc_1800208C8
0x1800208a5  lea     rax, WPP_GLOBAL_Control
0x1800208ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800208b3  cmp     rcx, rax
0x1800208b6  jz      short loc_1800208EB
0x1800208b8  test    [rcx+1Ch], r14b
0x1800208bc  jz      short loc_1800208EB
0x1800208be  mov     edx, 11h
0x1800208c3  jmp     loc_180020720
0x1800208c8  mov     rbx, [rbp+hExistingToken]
0x1800208cc  mov     [rbp+hExistingToken], 0
0x1800208d4  mov     rcx, [rsi]; hObject
0x1800208d7  mov     [rsi], rbx
0x1800208da  lea     rax, [rcx+1]
0x1800208de  cmp     rax, r14
0x1800208e1  jbe     short loc_1800208E9
0x1800208e3  call    cs:__imp_CloseHandle
0x1800208e9  xor     ebx, ebx
0x1800208eb  mov     rcx, [rbp+hExistingToken]; hObject
0x1800208ef  lea     rax, [rcx+1]
0x1800208f3  cmp     rax, r14
0x1800208f6  jbe     short loc_1800208FE
0x1800208f8  call    cs:__imp_CloseHandle
0x1800208fe  mov     eax, ebx
0x180020900  mov     rbx, [rsp+20h+arg_8]
0x180020905  mov     rsi, [rsp+20h+arg_10]
0x18002090a  add     rsp, 20h
0x18002090e  pop     r14
0x180020910  pop     rdi
0x180020911  pop     rbp
0x180020912  retn
```
