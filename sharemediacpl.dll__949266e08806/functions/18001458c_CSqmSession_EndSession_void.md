# CSqmSession::EndSession(void)

- ea: `0x18001458c`
- end: `0x1800146e0`
- name: `?EndSession@CSqmSession@@QEAAJXZ`
- size: `340`
- prototype: `__int64 __fastcall(CSqmSession *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180015dd8`
- `0x180016010`

## callees

- `0x180001d60`
- `0x180003860`
- `0x180003888`
- `0x180006ca8`
- `0x180012dd8`
- `0x18001458c`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180014681`
- `KERNEL32!SetLastError` at `0x180014681`
- `KERNEL32!GetTempPath2W` at `0x1800145fe`
- `KERNEL32!GetTempPath2W` at `0x1800145fe`
- `KERNEL32!GetLastError` at `0x18001460d`
- `KERNEL32!GetLastError` at `0x18001460d`

## pseudocode

```c
__int64 __fastcall CSqmSession::EndSession(CSqmSession *this)
{
  _QWORD *v2; // rcx
  unsigned int v3; // ebx
  signed int LastError; // eax
  _BYTE v6[528]; // [rsp+30h] [rbp-438h] BYREF
  unsigned __int16 v7[264]; // [rsp+240h] [rbp-228h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_6a02d0885a10324ba7005a50ff1b4315_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v3 = 0;
  if ( *((_QWORD *)this + 5) )
  {
    if ( (unsigned int)GetTempPath2W(261, v6) - 1 <= 0x103 )
      goto LABEL_9;
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( !v3 )
    {
LABEL_9:
      StringCchPrintfW(v7, 0x105u, L"%ws\\%ws", v6, L"ShareCPLlog%02d.sqm");
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_6a02d0885a10324ba7005a50ff1b4315_Traceguids, v7);
      SetLastError(0);
      *((_QWORD *)this + 5) = 0;
    }
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x20) != 0 )
    WPP_SF_d(v2[2], 21, &WPP_6a02d0885a10324ba7005a50ff1b4315_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x18001458c  mov     [rsp+arg_8], rbx
0x180014591  mov     [rsp+arg_10], rbp
0x180014596  push    rdi
0x180014597  sub     rsp, 460h
0x18001459e  mov     rax, cs:__security_cookie
0x1800145a5  xor     rax, rsp
0x1800145a8  mov     [rsp+468h+var_18], rax
0x1800145b0  mov     rdi, rcx
0x1800145b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800145ba  lea     rbp, WPP_GLOBAL_Control
0x1800145c1  cmp     rcx, rbp
0x1800145c4  jz      short loc_1800145E8
0x1800145c6  test    byte ptr [rcx+1Ch], 20h
0x1800145ca  jz      short loc_1800145E8
0x1800145cc  mov     rcx, [rcx+10h]
0x1800145d0  lea     r8, WPP_6a02d0885a10324ba7005a50ff1b4315_Traceguids
0x1800145d7  mov     edx, 13h
0x1800145dc  call    WPP_SF_
0x1800145e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800145e8  xor     ebx, ebx
0x1800145ea  cmp     [rdi+28h], rbx
0x1800145ee  jz      loc_180014696
0x1800145f4  lea     rdx, [rsp+468h+var_438]
0x1800145f9  mov     ecx, 105h
0x1800145fe  call    cs:__imp_GetTempPath2W
0x180014604  dec     eax
0x180014606  cmp     eax, 103h
0x18001460b  jbe     short loc_180014626
0x18001460d  call    cs:__imp_GetLastError
0x180014613  mov     ebx, eax
0x180014615  test    eax, eax
0x180014617  jle     short loc_180014622
0x180014619  movzx   ebx, ax
0x18001461c  or      ebx, 80070000h
0x180014622  test    ebx, ebx
0x180014624  jnz     short loc_18001468F
0x180014626  lea     rax, aSharecpllog02d; "ShareCPLlog%02d.sqm"
0x18001462d  mov     edx, 105h; unsigned __int64
0x180014632  lea     r9, [rsp+468h+var_438]
0x180014637  mov     [rsp+468h+var_448], rax
0x18001463c  lea     r8, aWsWs; "%ws\\%ws"
0x180014643  lea     rcx, [rsp+468h+var_228]; unsigned __int16 *
0x18001464b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180014650  mov     rcx, cs:WPP_GLOBAL_Control
0x180014657  cmp     rcx, rbp
0x18001465a  jz      short loc_18001467F
0x18001465c  test    byte ptr [rcx+1Ch], 8
0x180014660  jz      short loc_18001467F
0x180014662  mov     rcx, [rcx+10h]
0x180014666  lea     r9, [rsp+468h+var_228]
0x18001466e  mov     edx, 14h
0x180014673  lea     r8, WPP_6a02d0885a10324ba7005a50ff1b4315_Traceguids
0x18001467a  call    WPP_SF_S
0x18001467f  xor     ecx, ecx; dwErrCode
0x180014681  call    cs:__imp_SetLastError
0x180014687  mov     qword ptr [rdi+28h], 0
0x18001468f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014696  cmp     rcx, rbp
0x180014699  jz      short loc_1800146B9
0x18001469b  test    byte ptr [rcx+1Ch], 20h
0x18001469f  jz      short loc_1800146B9
0x1800146a1  mov     rcx, [rcx+10h]
0x1800146a5  lea     r8, WPP_6a02d0885a10324ba7005a50ff1b4315_Traceguids
0x1800146ac  mov     edx, 15h
0x1800146b1  mov     r9d, ebx
0x1800146b4  call    WPP_SF_d
0x1800146b9  mov     eax, ebx
0x1800146bb  mov     rcx, [rsp+468h+var_18]
0x1800146c3  xor     rcx, rsp; StackCookie
0x1800146c6  call    __security_check_cookie
0x1800146cb  lea     r11, [rsp+468h+var_8]
0x1800146d3  mov     rbx, [r11+18h]
0x1800146d7  mov     rbp, [r11+20h]
0x1800146db  mov     rsp, r11
0x1800146de  pop     rdi
0x1800146df  retn
```
