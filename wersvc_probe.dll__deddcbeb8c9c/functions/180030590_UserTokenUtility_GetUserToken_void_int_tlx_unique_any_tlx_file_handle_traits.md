# UserTokenUtility::GetUserToken(void *,int,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x180030590`
- end: `0x1800307a9`
- name: `?GetUserToken@UserTokenUtility@@SAJPEAXHPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `537`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x18002060c`
- `0x180022108`
- `0x180027460`

## callees

- `0x180004378`
- `0x180006a80`
- `0x180007cf8`
- `0x180011ef8`
- `0x1800304ac`
- `0x180030590`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180030616`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180030616`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030620`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800306c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030620`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800306c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800305e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030723`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003076f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030784`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030799`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800305e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030723`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003076f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030784`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030799`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x1800306bd`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x1800306bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UserTokenUtility::GetUserToken(HANDLE ProcessHandle, __int64 a2, void **a3)
{
  void *v5; // rcx
  unsigned int TokenSessionId; // ebx
  void **v7; // rax
  signed int v8; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rax
  signed int LastError; // eax
  HANDLE v13; // rax
  void *v14; // rcx
  HANDLE v16; // [rsp+50h] [rbp+20h] BYREF
  unsigned int v17; // [rsp+58h] [rbp+28h] BYREF
  HANDLE v18; // [rsp+68h] [rbp+38h] BYREF

  v18 = 0;
  v16 = 0;
  v17 = 0;
  if ( ProcessHandle && a3 )
  {
    v5 = *a3;
    *a3 = 0;
    if ( (unsigned __int64)v5 + 1 > 1 )
      CloseHandle(v5);
    if ( !(unsigned __int8)IsQueryUserTokenPresent() )
    {
      TokenSessionId = -2147024846;
      goto LABEL_31;
    }
    v7 = (void **)tlx::replace<tlx::file_handle_traits>(&v18);
    if ( OpenProcessToken(ProcessHandle, 0x4Fu, v7) )
    {
      TokenSessionId = UserTokenUtility::GetTokenSessionId(v18, &v17);
      if ( (TokenSessionId & 0x80000000) == 0 )
      {
        v11 = tlx::replace<tlx::file_handle_traits>(&v16);
        if ( (unsigned int)QueryUserToken(v17, v11) )
        {
          v13 = v16;
          v16 = 0;
          v14 = *a3;
          *a3 = v13;
          if ( (unsigned __int64)v14 + 1 > 1 )
            CloseHandle(v14);
          TokenSessionId = 0;
        }
        else
        {
          LastError = GetLastError();
          TokenSessionId = LastError;
          if ( LastError > 0 )
            TokenSessionId = (unsigned __int16)LastError | 0x80070000;
          if ( TokenSessionId != -2147024846 )
          {
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v10 = 26;
              goto LABEL_13;
            }
          }
        }
      }
      else
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v10 = 25;
          goto LABEL_13;
        }
      }
    }
    else
    {
      v8 = GetLastError();
      TokenSessionId = v8;
      if ( v8 > 0 )
        TokenSessionId = (unsigned __int16)v8 | 0x80070000;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v10 = 24;
LABEL_13:
        WPP_SF_d(v9[2], v10, &WPP_a23aa53e43603591c4e5d6b4fc0b4a04_Traceguids, TokenSessionId);
      }
    }
  }
  else
  {
    TokenSessionId = -2147024809;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_a23aa53e43603591c4e5d6b4fc0b4a04_Traceguids);
  }
LABEL_31:
  if ( (unsigned __int64)v16 + 1 > 1 )
    CloseHandle(v16);
  if ( (unsigned __int64)v18 + 1 > 1 )
    CloseHandle(v18);
  return TokenSessionId;
}

```

## disassembly

```asm
0x180030590  mov     [rsp-18h+arg_8], edx
0x180030594  push    rbp
0x180030595  push    rbx
0x180030596  push    rdi
0x180030597  mov     rbp, rsp
0x18003059a  sub     rsp, 30h
0x18003059e  mov     rdi, r8
0x1800305a1  mov     rbx, rcx
0x1800305a4  mov     [rbp+arg_18], 0
0x1800305ac  mov     [rbp+arg_0], 0
0x1800305b4  mov     [rbp+hObject], 0
0x1800305bc  mov     [rbp+arg_8], 0
0x1800305c3  test    rcx, rcx
0x1800305c6  jz      loc_18003072D
0x1800305cc  test    r8, r8
0x1800305cf  jz      loc_18003072D
0x1800305d5  mov     rcx, [r8]; hObject
0x1800305d8  mov     qword ptr [r8], 0
0x1800305df  lea     rax, [rcx+1]
0x1800305e3  cmp     rax, 1
0x1800305e7  jbe     short loc_1800305EF
0x1800305e9  call    cs:__imp_CloseHandle
0x1800305ef  call    IsQueryUserTokenPresent
0x1800305f4  test    al, al
0x1800305f6  jnz     short loc_180030602
0x1800305f8  mov     ebx, 80070032h
0x1800305fd  jmp     loc_180030761
0x180030602  lea     rcx, [rbp+arg_18]
0x180030606  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18003060b  mov     r8, rax; TokenHandle
0x18003060e  mov     edx, 4Fh ; 'O'; DesiredAccess
0x180030613  mov     rcx, rbx; ProcessHandle
0x180030616  call    cs:__imp_OpenProcessToken
0x18003061c  test    eax, eax
0x18003061e  jnz     short loc_180030673
0x180030620  call    cs:__imp_GetLastError
0x180030626  mov     ebx, eax
0x180030628  test    eax, eax
0x18003062a  jle     short loc_180030635
0x18003062c  movzx   ebx, ax
0x18003062f  or      ebx, 80070000h
0x180030635  lea     rax, WPP_GLOBAL_Control
0x18003063c  mov     rcx, cs:WPP_GLOBAL_Control
0x180030643  cmp     rcx, rax
0x180030646  jz      loc_180030761
0x18003064c  test    byte ptr [rcx+1Ch], 1
0x180030650  jz      loc_180030761
0x180030656  mov     edx, 18h
0x18003065b  mov     r9d, ebx
0x18003065e  lea     r8, WPP_a23aa53e43603591c4e5d6b4fc0b4a04_Traceguids
0x180030665  mov     rcx, [rcx+10h]
0x180030669  call    WPP_SF_d
0x18003066e  jmp     loc_180030761
0x180030673  lea     rdx, [rbp+arg_8]; unsigned int *
0x180030677  mov     rcx, [rbp+arg_18]; void *
0x18003067b  call    ?GetTokenSessionId@UserTokenUtility@@SAJPEAXPEAK@Z; UserTokenUtility::GetTokenSessionId(void *,ulong *)
0x180030680  mov     ebx, eax
0x180030682  test    eax, eax
0x180030684  jns     short loc_1800306AE
0x180030686  lea     rax, WPP_GLOBAL_Control
0x18003068d  mov     rcx, cs:WPP_GLOBAL_Control
0x180030694  cmp     rcx, rax
0x180030697  jz      loc_180030761
0x18003069d  test    byte ptr [rcx+1Ch], 1
0x1800306a1  jz      loc_180030761
0x1800306a7  mov     edx, 19h
0x1800306ac  jmp     short loc_18003065B
0x1800306ae  lea     rcx, [rbp+arg_0]
0x1800306b2  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x1800306b7  mov     rdx, rax
0x1800306ba  mov     ecx, [rbp+arg_8]
0x1800306bd  call    cs:__imp_QueryUserToken
0x1800306c3  test    eax, eax
0x1800306c5  jnz     short loc_180030707
0x1800306c7  call    cs:__imp_GetLastError
0x1800306cd  mov     ebx, eax
0x1800306cf  test    eax, eax
0x1800306d1  jle     short loc_1800306DC
0x1800306d3  movzx   ebx, ax
0x1800306d6  or      ebx, 80070000h
0x1800306dc  cmp     ebx, 80070032h
0x1800306e2  jz      short loc_180030761
0x1800306e4  lea     rax, WPP_GLOBAL_Control
0x1800306eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800306f2  cmp     rcx, rax
0x1800306f5  jz      short loc_180030761
0x1800306f7  test    byte ptr [rcx+1Ch], 1
0x1800306fb  jz      short loc_180030761
0x1800306fd  mov     edx, 1Ah
0x180030702  jmp     loc_18003065B
0x180030707  mov     rax, [rbp+arg_0]
0x18003070b  mov     [rbp+arg_0], 0
0x180030713  mov     rcx, [rdi]; hObject
0x180030716  mov     [rdi], rax
0x180030719  lea     rax, [rcx+1]
0x18003071d  cmp     rax, 1
0x180030721  jbe     short loc_180030729
0x180030723  call    cs:__imp_CloseHandle
0x180030729  xor     ebx, ebx
0x18003072b  jmp     short loc_180030761
0x18003072d  mov     ebx, 80070057h
0x180030732  lea     rax, WPP_GLOBAL_Control
0x180030739  mov     rcx, cs:WPP_GLOBAL_Control
0x180030740  cmp     rcx, rax
0x180030743  jz      short loc_180030761
0x180030745  test    byte ptr [rcx+1Ch], 1
0x180030749  jz      short loc_180030761
0x18003074b  mov     edx, 17h
0x180030750  lea     r8, WPP_a23aa53e43603591c4e5d6b4fc0b4a04_Traceguids
0x180030757  mov     rcx, [rcx+10h]
0x18003075b  call    WPP_SF_
0x180030760  nop
0x180030761  mov     rcx, [rbp+hObject]; hObject
0x180030765  lea     rax, [rcx+1]
0x180030769  cmp     rax, 1
0x18003076d  jbe     short loc_180030776
0x18003076f  call    cs:__imp_CloseHandle
0x180030775  nop
0x180030776  mov     rcx, [rbp+arg_0]; hObject
0x18003077a  lea     rax, [rcx+1]
0x18003077e  cmp     rax, 1
0x180030782  jbe     short loc_18003078B
0x180030784  call    cs:__imp_CloseHandle
0x18003078a  nop
0x18003078b  mov     rcx, [rbp+arg_18]; hObject
0x18003078f  lea     rax, [rcx+1]
0x180030793  cmp     rax, 1
0x180030797  jbe     short loc_18003079F
0x180030799  call    cs:__imp_CloseHandle
0x18003079f  mov     eax, ebx
0x1800307a1  add     rsp, 30h
0x1800307a5  pop     rdi
0x1800307a6  pop     rbx
0x1800307a7  pop     rbp
0x1800307a8  retn
```
