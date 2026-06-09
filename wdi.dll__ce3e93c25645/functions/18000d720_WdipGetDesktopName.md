# WdipGetDesktopName

- ea: `0x18000d720`
- end: `0x18000d9a5`
- name: `WdipGetDesktopName`
- size: `645`
- prototype: `__int64 __fastcall(char *pvInfo, DWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a420`
- `0x18000a744`
- `0x18000ab6c`

## callees

- `0x180002ba0`
- `0x18000d720`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d781`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d7e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d8c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d94f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d781`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d7e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d8c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d94f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d7c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d7c6`
- `USER32!GetProcessWindowStation` at `0x18000d767`
- `USER32!GetProcessWindowStation` at `0x18000d767`
- `USER32!GetUserObjectInformationW` at `0x18000d7c0`
- `USER32!GetUserObjectInformationW` at `0x18000d821`
- `USER32!GetUserObjectInformationW` at `0x18000d8b8`
- `USER32!GetUserObjectInformationW` at `0x18000d941`
- `USER32!GetUserObjectInformationW` at `0x18000d7c0`
- `USER32!GetUserObjectInformationW` at `0x18000d821`
- `USER32!GetUserObjectInformationW` at `0x18000d8b8`
- `USER32!GetUserObjectInformationW` at `0x18000d941`
- `USER32!GetThreadDesktop` at `0x18000d7ce`
- `USER32!GetThreadDesktop` at `0x18000d7ce`

## pseudocode

```c
__int64 __fastcall WdipGetDesktopName(char *pvInfo, DWORD *a2)
{
  signed int v4; // ebx
  HWINSTA ProcessWindowStation; // rbp
  signed int LastError; // eax
  DWORD CurrentThreadId; // eax
  HDESK ThreadDesktop; // r15
  signed int v9; // eax
  DWORD v10; // edx
  unsigned int v11; // eax
  DWORD v12; // edi
  signed int v13; // eax
  unsigned int v14; // edi
  char *v15; // r8
  signed int v16; // eax
  DWORD nLengthNeeded; // [rsp+60h] [rbp+8h] BYREF
  DWORD lpnLengthNeeded; // [rsp+68h] [rbp+10h] BYREF

  lpnLengthNeeded = 0;
  nLengthNeeded = 0;
  if ( a2 )
  {
    ProcessWindowStation = GetProcessWindowStation();
    if ( (((unsigned __int64)ProcessWindowStation + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
      goto LABEL_8;
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 >= 0 )
    {
LABEL_8:
      GetUserObjectInformationW(ProcessWindowStation, 2, 0, 0, &nLengthNeeded);
      CurrentThreadId = GetCurrentThreadId();
      ThreadDesktop = GetThreadDesktop(CurrentThreadId);
      if ( (((unsigned __int64)ThreadDesktop + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
        goto LABEL_13;
      v9 = GetLastError();
      v4 = v9;
      if ( v9 > 0 )
        v4 = (unsigned __int16)v9 | 0x80070000;
      if ( v4 >= 0 )
      {
LABEL_13:
        GetUserObjectInformationW(ThreadDesktop, 2, 0, 0, &lpnLengthNeeded);
        v10 = lpnLengthNeeded + nLengthNeeded;
        if ( lpnLengthNeeded + nLengthNeeded >= lpnLengthNeeded )
        {
          if ( v10 + 16 >= v10 )
          {
            v11 = (v10 + 23) & 0xFFFFFFF8;
            if ( pvInfo )
            {
              v12 = *a2;
              if ( *a2 >= v11 )
              {
                if ( GetUserObjectInformationW(ProcessWindowStation, 2, pvInfo, v12, &nLengthNeeded) )
                  goto LABEL_26;
                v13 = GetLastError();
                v4 = v13;
                if ( v13 > 0 )
                  v4 = (unsigned __int16)v13 | 0x80070000;
                if ( v4 >= 0 )
                {
LABEL_26:
                  if ( lpnLengthNeeded )
                  {
                    v14 = v12 - nLengthNeeded;
                    if ( v14 >= 2 )
                    {
                      v15 = &pvInfo[2 * ((unsigned __int64)nLengthNeeded >> 1)];
                      *((_WORD *)v15 - 1) = 92;
                      if ( GetUserObjectInformationW(ThreadDesktop, 2, v15, v14 - 2, &lpnLengthNeeded) )
                      {
                        return 0;
                      }
                      else
                      {
                        v16 = GetLastError();
                        v4 = v16;
                        if ( v16 > 0 )
                          v4 = (unsigned __int16)v16 | 0x80070000;
                        if ( v4 < 0 )
                          WdipTraceError(
                            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\utils.cpp",
                            (int)L"WdipGetDesktopName",
                            536,
                            (int)L"Error = %d",
                            v4);
                      }
                    }
                    else
                    {
                      v4 = -2147024662;
                      WdipTraceError(
                        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\utils.cpp",
                        (int)L"WdipGetDesktopName",
                        525,
                        (int)L"Error = %d",
                        234);
                    }
                  }
                  else
                  {
                    return (unsigned int)-2147467259;
                  }
                }
                else
                {
                  WdipTraceError(
                    (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\utils.cpp",
                    (int)L"WdipGetDesktopName",
                    512,
                    (int)L"Error = %d",
                    v4);
                }
              }
              else
              {
                *a2 = v11;
                v4 = -2147024662;
                WdipTraceError(
                  (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\utils.cpp",
                  (int)L"WdipGetDesktopName",
                  500,
                  (int)L"Error = %d",
                  234);
              }
            }
            else
            {
              v4 = 0;
              *a2 = v11;
            }
          }
          else
          {
            v4 = -2147024362;
            WdipTraceError(
              (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\utils.cpp",
              (int)L"WdipGetDesktopName",
              488,
              (int)L"Error = %d",
              22);
          }
        }
        else
        {
          v4 = -2147024362;
          WdipTraceError(
            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\utils.cpp",
            (int)L"WdipGetDesktopName",
            485,
            (int)L"Error = %d",
            22);
        }
      }
      else
      {
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\utils.cpp",
          (int)L"WdipGetDesktopName",
          475,
          (int)L"Error = %d",
          v4);
      }
    }
    else
    {
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\utils.cpp",
        (int)L"WdipGetDesktopName",
        465,
        (int)L"Error = %d",
        v4);
    }
  }
  else
  {
    v4 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\utils.cpp",
      (int)L"WdipGetDesktopName",
      459,
      (int)L"Error = %d",
      87);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000d720  mov     rax, rsp
0x18000d723  mov     [rax+18h], rbx
0x18000d727  mov     [rax+20h], rbp
0x18000d72b  push    rsi
0x18000d72c  push    rdi
0x18000d72d  push    r13
0x18000d72f  push    r14
0x18000d731  push    r15
0x18000d733  sub     rsp, 30h
0x18000d737  mov     dword ptr [rax+10h], 0
0x18000d73e  mov     rsi, rdx
0x18000d741  mov     dword ptr [rax+8], 0
0x18000d748  mov     r14, rcx
0x18000d74b  test    rdx, rdx
0x18000d74e  jnz     short loc_18000D767
0x18000d750  mov     ebx, 80070057h
0x18000d755  mov     dword ptr [rax-38h], 57h ; 'W'
0x18000d75c  mov     r8d, 1CBh
0x18000d762  jmp     loc_18000D972
0x18000d767  call    cs:__imp_GetProcessWindowStation
0x18000d76d  mov     rbp, rax
0x18000d770  mov     r13d, 80070000h
0x18000d776  inc     rax
0x18000d779  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000d77f  jnz     short loc_18000D7A9
0x18000d781  call    cs:__imp_GetLastError
0x18000d787  mov     ebx, eax
0x18000d789  test    eax, eax
0x18000d78b  jle     short loc_18000D793
0x18000d78d  movzx   ebx, ax
0x18000d790  or      ebx, r13d
0x18000d793  test    ebx, ebx
0x18000d795  jns     short loc_18000D7A9
0x18000d797  movzx   eax, bx
0x18000d79a  mov     r8d, 1D1h
0x18000d7a0  mov     dword ptr [rsp+58h+lpnLengthNeeded], eax
0x18000d7a4  jmp     loc_18000D972
0x18000d7a9  xor     r9d, r9d; nLength
0x18000d7ac  lea     rax, [rsp+58h+nLengthNeeded]
0x18000d7b1  xor     r8d, r8d; pvInfo
0x18000d7b4  mov     [rsp+58h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18000d7b9  mov     rcx, rbp; hObj
0x18000d7bc  lea     edx, [r9+2]; nIndex
0x18000d7c0  call    cs:__imp_GetUserObjectInformationW
0x18000d7c6  call    cs:__imp_GetCurrentThreadId
0x18000d7cc  mov     ecx, eax; dwThreadId
0x18000d7ce  call    cs:__imp_GetThreadDesktop
0x18000d7d4  mov     r15, rax
0x18000d7d7  inc     rax
0x18000d7da  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000d7e0  jnz     short loc_18000D80A
0x18000d7e2  call    cs:__imp_GetLastError
0x18000d7e8  mov     ebx, eax
0x18000d7ea  test    eax, eax
0x18000d7ec  jle     short loc_18000D7F4
0x18000d7ee  movzx   ebx, ax
0x18000d7f1  or      ebx, r13d
0x18000d7f4  test    ebx, ebx
0x18000d7f6  jns     short loc_18000D80A
0x18000d7f8  movzx   eax, bx
0x18000d7fb  mov     r8d, 1DBh
0x18000d801  mov     dword ptr [rsp+58h+lpnLengthNeeded], eax
0x18000d805  jmp     loc_18000D972
0x18000d80a  xor     r9d, r9d; nLength
0x18000d80d  lea     rax, [rsp+58h+arg_8]
0x18000d812  xor     r8d, r8d; pvInfo
0x18000d815  mov     [rsp+58h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18000d81a  mov     rcx, r15; hObj
0x18000d81d  lea     edx, [r9+2]; nIndex
0x18000d821  call    cs:__imp_GetUserObjectInformationW
0x18000d827  mov     edx, [rsp+58h+nLengthNeeded]
0x18000d82b  add     edx, [rsp+58h+arg_8]
0x18000d82f  cmp     edx, [rsp+58h+arg_8]
0x18000d833  jnb     short loc_18000D84D
0x18000d835  mov     ebx, 80070216h
0x18000d83a  mov     dword ptr [rsp+58h+lpnLengthNeeded], 216h
0x18000d842  mov     r8d, 1E5h
0x18000d848  jmp     loc_18000D972
0x18000d84d  lea     eax, [rdx+10h]
0x18000d850  cmp     eax, edx
0x18000d852  jnb     short loc_18000D86C
0x18000d854  mov     ebx, 80070216h
0x18000d859  mov     dword ptr [rsp+58h+lpnLengthNeeded], 216h
0x18000d861  mov     r8d, 1E8h
0x18000d867  jmp     loc_18000D972
0x18000d86c  add     eax, 7
0x18000d86f  and     eax, 0FFFFFFF8h
0x18000d872  test    r14, r14
0x18000d875  jnz     short loc_18000D880
0x18000d877  xor     ebx, ebx
0x18000d879  mov     [rsi], eax
0x18000d87b  jmp     loc_18000D98C
0x18000d880  mov     edi, [rsi]
0x18000d882  cmp     edi, eax
0x18000d884  jnb     short loc_18000D8A0
0x18000d886  mov     [rsi], eax
0x18000d888  mov     ebx, 800700EAh
0x18000d88d  mov     dword ptr [rsp+58h+lpnLengthNeeded], 0EAh
0x18000d895  mov     r8d, 1F4h
0x18000d89b  jmp     loc_18000D972
0x18000d8a0  lea     rax, [rsp+58h+nLengthNeeded]
0x18000d8a5  mov     r9d, edi; nLength
0x18000d8a8  mov     r8, r14; pvInfo
0x18000d8ab  mov     [rsp+58h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18000d8b0  mov     edx, 2; nIndex
0x18000d8b5  mov     rcx, rbp; hObj
0x18000d8b8  call    cs:__imp_GetUserObjectInformationW
0x18000d8be  test    eax, eax
0x18000d8c0  jnz     short loc_18000D8EA
0x18000d8c2  call    cs:__imp_GetLastError
0x18000d8c8  mov     ebx, eax
0x18000d8ca  test    eax, eax
0x18000d8cc  jle     short loc_18000D8D4
0x18000d8ce  movzx   ebx, ax
0x18000d8d1  or      ebx, r13d
0x18000d8d4  test    ebx, ebx
0x18000d8d6  jns     short loc_18000D8EA
0x18000d8d8  movzx   eax, bx
0x18000d8db  mov     r8d, 200h
0x18000d8e1  mov     dword ptr [rsp+58h+lpnLengthNeeded], eax
0x18000d8e5  jmp     loc_18000D972
0x18000d8ea  cmp     [rsp+58h+arg_8], 0
0x18000d8ef  jnz     short loc_18000D8FB
0x18000d8f1  mov     ebx, 80004005h
0x18000d8f6  jmp     loc_18000D98C
0x18000d8fb  sub     edi, [rsp+58h+nLengthNeeded]
0x18000d8ff  cmp     edi, 2
0x18000d902  jnb     short loc_18000D919
0x18000d904  mov     ebx, 800700EAh
0x18000d909  mov     dword ptr [rsp+58h+lpnLengthNeeded], 0EAh
0x18000d911  mov     r8d, 20Dh
0x18000d917  jmp     short loc_18000D972
0x18000d919  mov     eax, [rsp+58h+nLengthNeeded]
0x18000d91d  lea     r9d, [rdi-2]; nLength
0x18000d921  shr     rax, 1
0x18000d924  mov     edx, 2; nIndex
0x18000d929  mov     rcx, r15; hObj
0x18000d92c  lea     r8, [r14+rax*2]; pvInfo
0x18000d930  lea     rax, [rsp+58h+arg_8]
0x18000d935  mov     word ptr [r8-2], 5Ch ; '\'
0x18000d93c  mov     [rsp+58h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18000d941  call    cs:__imp_GetUserObjectInformationW
0x18000d947  test    eax, eax
0x18000d949  jz      short loc_18000D94F
0x18000d94b  xor     ebx, ebx
0x18000d94d  jmp     short loc_18000D98C
0x18000d94f  call    cs:__imp_GetLastError
0x18000d955  mov     ebx, eax
0x18000d957  test    eax, eax
0x18000d959  jle     short loc_18000D961
0x18000d95b  movzx   ebx, ax
0x18000d95e  or      ebx, r13d
0x18000d961  test    ebx, ebx
0x18000d963  jns     short loc_18000D98C
0x18000d965  movzx   ecx, bx
0x18000d968  mov     r8d, 218h; int
0x18000d96e  mov     dword ptr [rsp+58h+lpnLengthNeeded], ecx; Args
0x18000d972  lea     r9, aErrorD_0; "Error = %d"
0x18000d979  lea     rdx, aWdipgetdesktop; "WdipGetDesktopName"
0x18000d980  lea     rcx, aClientcoreBase_1; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000d987  call    WdipTraceError
0x18000d98c  mov     rbp, [rsp+58h+arg_18]
0x18000d991  mov     eax, ebx
0x18000d993  mov     rbx, [rsp+58h+arg_10]
0x18000d998  add     rsp, 30h
0x18000d99c  pop     r15
0x18000d99e  pop     r14
0x18000d9a0  pop     r13
0x18000d9a2  pop     rdi
0x18000d9a3  pop     rsi
0x18000d9a4  retn
```
