# IsolationAwareDialogBoxParamW

- ea: `0x1800116a4`
- end: `0x180011772`
- name: `IsolationAwareDialogBoxParamW`
- size: `206`
- prototype: `__int64 __fastcall(HINSTANCE hInstance, LPCWSTR lpTemplateName, HWND hWndParent)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000dd64`
- `0x18000de44`
- `0x18000df24`

## callees

- `0x18000c6ec`
- `0x1800116a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011746`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e408`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011746`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e408`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011767`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e428`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011767`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e428`
- `KERNEL32!DeactivateActCtx` at `0x18001175b`
- `KERNEL32!DeactivateActCtx` at `0x18002e41c`
- `KERNEL32!DeactivateActCtx` at `0x18001175b`
- `KERNEL32!DeactivateActCtx` at `0x18002e41c`
- `USER32!DialogBoxParamW` at `0x18001171d`
- `USER32!DialogBoxParamW` at `0x18001171d`

## pseudocode

```c
INT_PTR __fastcall IsolationAwareDialogBoxParamW(HINSTANCE hInstance, LPCWSTR lpTemplateName, HWND hWndParent)
{
  INT_PTR v7; // rax
  INT_PTR v8; // rsi
  int v9; // edi
  DWORD LastError; // ebx
  ULONG_PTR ulCookie; // [rsp+68h] [rbp+20h] BYREF

  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return -1;
  }
  v7 = DialogBoxParamW(
         hInstance,
         lpTemplateName,
         hWndParent,
         (DLGPROC)ATL::CDialogImplBaseT<ATL::CWindow>::StartDialogProc,
         0);
  v8 = v7;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( v7 == -1 )
    {
      v9 = 1;
      LastError = GetLastError();
    }
    else
    {
      v9 = 0;
      LastError = 0;
    }
    DeactivateActCtx(0, ulCookie);
    if ( v9 )
      SetLastError(LastError);
  }
  return v8;
}

```

## disassembly

```asm
0x1800116a4  mov     rax, rsp
0x1800116a7  mov     [rax+8], rbx
0x1800116ab  mov     [rax+10h], rsi
0x1800116af  mov     [rax+20h], r9
0x1800116b3  push    rdi
0x1800116b4  sub     rsp, 40h
0x1800116b8  mov     rbx, r8
0x1800116bb  mov     rdi, rdx
0x1800116be  mov     rsi, rcx
0x1800116c1  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFFh
0x1800116c9  mov     qword ptr [rax+20h], 0
0x1800116d1  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800116d8  jnz     short loc_180011704
0x1800116da  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800116e1  jnz     short loc_180011704
0x1800116e3  lea     rcx, [rax+20h]; lpCookie
0x1800116e7  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x1800116ec  test    eax, eax
0x1800116ee  jnz     short loc_180011704
0x1800116f0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800116f4  mov     rbx, [rsp+48h+arg_0]
0x1800116f9  mov     rsi, [rsp+48h+arg_8]
0x1800116fe  add     rsp, 40h
0x180011702  pop     rdi
0x180011703  retn
0x180011704  mov     [rsp+48h+dwInitParam], 0; dwInitParam
0x18001170d  lea     r9, ?StartDialogProc@?$CDialogImplBaseT@VCWindow@ATL@@@ATL@@SA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x180011714  mov     r8, rbx; hWndParent
0x180011717  mov     rdx, rdi; lpTemplateName
0x18001171a  mov     rcx, rsi; hInstance
0x18001171d  call    cs:__imp_DialogBoxParamW
0x180011723  mov     rsi, rax
0x180011726  mov     [rsp+48h+var_18], rax
0x18001172b  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180011732  jz      short loc_18001173D
0x180011734  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18001173b  jnz     short loc_18001176D
0x18001173d  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180011741  jnz     short loc_180011750
0x180011743  lea     edi, [rsi+2]
0x180011746  call    cs:__imp_GetLastError
0x18001174c  mov     ebx, eax
0x18001174e  jmp     short loc_180011754
0x180011750  xor     edi, edi
0x180011752  xor     ebx, ebx
0x180011754  mov     rdx, [rsp+48h+ulCookie]; ulCookie
0x180011759  xor     ecx, ecx; dwFlags
0x18001175b  call    cs:__imp_DeactivateActCtx
0x180011761  test    edi, edi
0x180011763  jz      short loc_18001176D
0x180011765  mov     ecx, ebx; dwErrCode
0x180011767  call    cs:__imp_SetLastError
0x18001176d  mov     rax, rsi
0x180011770  jmp     short loc_1800116F4
0x18002e3df  push    rbx
0x18002e3e1  push    rbp
0x18002e3e2  push    rdi
0x18002e3e3  sub     rsp, 30h
0x18002e3e7  mov     rbp, rdx
0x18002e3ea  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18002e3f1  jz      short loc_18002E3FC
0x18002e3f3  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18002e3fa  jnz     short loc_18002E42F
0x18002e3fc  cmp     qword ptr [rbp+30h], 0FFFFFFFFFFFFFFFFh
0x18002e401  jnz     short loc_18002E412
0x18002e403  mov     edi, 1
0x18002e408  call    cs:__imp_GetLastError
0x18002e40e  mov     ebx, eax
0x18002e410  jmp     short loc_18002E416
0x18002e412  xor     edi, edi
0x18002e414  xor     ebx, ebx
0x18002e416  mov     rdx, [rbp+68h]; ulCookie
0x18002e41a  xor     ecx, ecx; dwFlags
0x18002e41c  call    cs:__imp_DeactivateActCtx
0x18002e422  test    edi, edi
0x18002e424  jz      short loc_18002E42F
0x18002e426  mov     ecx, ebx; dwErrCode
0x18002e428  call    cs:__imp_SetLastError
0x18002e42e  nop
0x18002e42f  add     rsp, 30h
0x18002e433  pop     rdi
0x18002e434  pop     rbp
0x18002e435  pop     rbx
0x18002e436  retn
```
