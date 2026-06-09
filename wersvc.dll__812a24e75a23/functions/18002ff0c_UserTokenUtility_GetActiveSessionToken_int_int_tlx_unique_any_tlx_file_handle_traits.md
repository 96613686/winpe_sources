# UserTokenUtility::GetActiveSessionToken(int,int,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x18002ff0c`
- end: `0x1800300ba`
- name: `?GetActiveSessionToken@UserTokenUtility@@SAJHHPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `430`
- prototype: `__int64 __fastcall(__int64, __int64, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18002060c`

## callees

- `0x180004378`
- `0x180006a80`
- `0x180007cf8`
- `0x180011ef8`
- `0x18002ff0c`
- `0x1800309c4`
- `0x180030a58`
- `0x180034258`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ffc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ffc7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003007f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030095`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800300aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003007f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030095`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800300aa`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x18002ffbd`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x18002ffbd`

## pseudocode

```c
__int64 __fastcall UserTokenUtility::GetActiveSessionToken(__int64 a1, __int64 a2, void **a3)
{
  int active; // ebx
  void **v5; // rax
  signed int LastError; // eax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  void **v9; // rax
  int v10; // eax
  HANDLE v11; // rax
  void *v12; // rcx
  unsigned int v14; // [rsp+48h] [rbp+28h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp+30h] BYREF
  HANDLE TokenHandle; // [rsp+58h] [rbp+38h] BYREF

  v14 = 0;
  TokenHandle = 0;
  hObject = 0;
  if ( !a3 )
  {
    active = -2147024809;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_a23aa53e43603591c4e5d6b4fc0b4a04_Traceguids);
    goto LABEL_25;
  }
  if ( !(unsigned __int8)IsQueryUserTokenPresent() )
  {
    active = -2147024846;
    goto LABEL_25;
  }
  active = UserTokenUtility::QueryActiveSession(&v14);
  if ( active >= 0 )
  {
    if ( v14 == -1 )
    {
LABEL_9:
      active = -2147023888;
      goto LABEL_25;
    }
    v5 = tlx::replace<tlx::file_handle_traits>(&TokenHandle);
    if ( (unsigned int)QueryUserToken(v14, v5) )
    {
      if ( !(unsigned int)UtilIsUserAdmin(TokenHandle) )
        goto LABEL_9;
      v9 = tlx::replace<tlx::file_handle_traits>(&hObject);
      v10 = LUAGetElevatedToken(TokenHandle, v9);
      active = v10 | 0x10000000;
      if ( v10 < 0 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_25;
        v8 = 30;
LABEL_16:
        WPP_SF_d(v7[2], v8, WPP_a23aa53e43603591c4e5d6b4fc0b4a04_Traceguids, (unsigned int)active);
        goto LABEL_25;
      }
      v11 = hObject;
      hObject = 0;
      v12 = *a3;
      *a3 = v11;
      if ( (unsigned __int64)v12 + 1 > 1 )
        CloseHandle(v12);
      active = 0;
    }
    else
    {
      LastError = GetLastError();
      active = LastError;
      if ( LastError > 0 )
        active = (unsigned __int16)LastError | 0x80070000;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 29;
        goto LABEL_16;
      }
    }
  }
LABEL_25:
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  if ( (unsigned __int64)TokenHandle + 1 > 1 )
    CloseHandle(TokenHandle);
  return (unsigned int)active;
}

```

## disassembly

```asm
0x18002ff0c  mov     [rsp-18h+arg_8], edx
0x18002ff10  push    rbp
0x18002ff11  push    rbx
0x18002ff12  push    rdi
0x18002ff13  mov     rbp, rsp
0x18002ff16  sub     rsp, 20h
0x18002ff1a  mov     rdi, r8
0x18002ff1d  mov     [rbp+arg_8], 0
0x18002ff24  mov     [rbp+TokenHandle], 0
0x18002ff2c  mov     [rbp+hObject], 0
0x18002ff34  test    r8, r8
0x18002ff37  jnz     short loc_18002FF78
0x18002ff39  mov     ebx, 80070057h
0x18002ff3e  lea     rax, WPP_GLOBAL_Control
0x18002ff45  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ff4c  cmp     rcx, rax
0x18002ff4f  jz      loc_180030087
0x18002ff55  test    byte ptr [rcx+1Ch], 1
0x18002ff59  jz      loc_180030087
0x18002ff5f  lea     edx, [r8+1Ch]
0x18002ff63  lea     r8, WPP_a23aa53e43603591c4e5d6b4fc0b4a04_Traceguids
0x18002ff6a  mov     rcx, [rcx+10h]
0x18002ff6e  call    WPP_SF_
0x18002ff73  jmp     loc_180030087
0x18002ff78  call    IsQueryUserTokenPresent
0x18002ff7d  test    al, al
0x18002ff7f  jnz     short loc_18002FF8B
0x18002ff81  mov     ebx, 80070032h
0x18002ff86  jmp     loc_180030087
0x18002ff8b  lea     rcx, [rbp+arg_8]; unsigned int *
0x18002ff8f  call    ?QueryActiveSession@UserTokenUtility@@SAJPEAK@Z; UserTokenUtility::QueryActiveSession(ulong *)
0x18002ff94  mov     ebx, eax
0x18002ff96  test    eax, eax
0x18002ff98  js      loc_180030087
0x18002ff9e  cmp     [rbp+arg_8], 0FFFFFFFFh
0x18002ffa2  jnz     short loc_18002FFAE
0x18002ffa4  mov     ebx, 800703F0h
0x18002ffa9  jmp     loc_180030087
0x18002ffae  lea     rcx, [rbp+TokenHandle]
0x18002ffb2  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18002ffb7  mov     rdx, rax
0x18002ffba  mov     ecx, [rbp+arg_8]
0x18002ffbd  call    cs:__imp_QueryUserToken
0x18002ffc3  test    eax, eax
0x18002ffc5  jnz     short loc_180030017
0x18002ffc7  call    cs:__imp_GetLastError
0x18002ffcd  mov     ebx, eax
0x18002ffcf  test    eax, eax
0x18002ffd1  jle     short loc_18002FFDC
0x18002ffd3  movzx   ebx, ax
0x18002ffd6  or      ebx, 80070000h
0x18002ffdc  lea     rax, WPP_GLOBAL_Control
0x18002ffe3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ffea  cmp     rcx, rax
0x18002ffed  jz      loc_180030087
0x18002fff3  test    byte ptr [rcx+1Ch], 1
0x18002fff7  jz      loc_180030087
0x18002fffd  mov     edx, 1Dh
0x180030002  mov     r9d, ebx
0x180030005  lea     r8, WPP_a23aa53e43603591c4e5d6b4fc0b4a04_Traceguids
0x18003000c  mov     rcx, [rcx+10h]
0x180030010  call    WPP_SF_d
0x180030015  jmp     short loc_180030087
0x180030017  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18003001b  call    ?UtilIsUserAdmin@@YAHPEAX@Z; UtilIsUserAdmin(void *)
0x180030020  test    eax, eax
0x180030022  jz      short loc_18002FFA4
0x180030024  lea     rcx, [rbp+hObject]
0x180030028  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18003002d  mov     rdx, rax; NewTokenHandle
0x180030030  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180030034  call    LUAGetElevatedToken
0x180030039  mov     ebx, eax
0x18003003b  or      ebx, 10000000h
0x180030041  jge     short loc_180030063
0x180030043  lea     rax, WPP_GLOBAL_Control
0x18003004a  mov     rcx, cs:WPP_GLOBAL_Control
0x180030051  cmp     rcx, rax
0x180030054  jz      short loc_180030087
0x180030056  test    byte ptr [rcx+1Ch], 1
0x18003005a  jz      short loc_180030087
0x18003005c  mov     edx, 1Eh
0x180030061  jmp     short loc_180030002
0x180030063  mov     rax, [rbp+hObject]
0x180030067  mov     [rbp+hObject], 0
0x18003006f  mov     rcx, [rdi]; hObject
0x180030072  mov     [rdi], rax
0x180030075  lea     rax, [rcx+1]
0x180030079  cmp     rax, 1
0x18003007d  jbe     short loc_180030085
0x18003007f  call    cs:__imp_CloseHandle
0x180030085  xor     ebx, ebx
0x180030087  mov     rcx, [rbp+hObject]; hObject
0x18003008b  lea     rax, [rcx+1]
0x18003008f  cmp     rax, 1
0x180030093  jbe     short loc_18003009C
0x180030095  call    cs:__imp_CloseHandle
0x18003009b  nop
0x18003009c  mov     rcx, [rbp+TokenHandle]; hObject
0x1800300a0  lea     rax, [rcx+1]
0x1800300a4  cmp     rax, 1
0x1800300a8  jbe     short loc_1800300B0
0x1800300aa  call    cs:__imp_CloseHandle
0x1800300b0  mov     eax, ebx
0x1800300b2  add     rsp, 20h
0x1800300b6  pop     rdi
0x1800300b7  pop     rbx
0x1800300b8  pop     rbp
0x1800300b9  retn
```
