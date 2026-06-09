# CSqmSession::UploadThreadProc(void *)

- ea: `0x1800150b0`
- end: `0x18001520d`
- name: `?UploadThreadProc@CSqmSession@@CAKPEAX@Z`
- size: `349`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180001d60`
- `0x180003860`
- `0x180006ca8`
- `0x180012dd8`
- `0x1800150b0`
- `0x1800152e4`
- `0x180015328`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180015195`
- `KERNEL32!SetLastError` at `0x180015195`
- `KERNEL32!GetTempPath2W` at `0x18001511c`
- `KERNEL32!GetTempPath2W` at `0x18001511c`
- `KERNEL32!GetLastError` at `0x18001512f`
- `KERNEL32!GetLastError` at `0x18001519b`
- `KERNEL32!GetLastError` at `0x18001512f`
- `KERNEL32!GetLastError` at `0x18001519b`
- `ntdll!WinSqmIsOptedIn` at `0x1800150ff`
- `ntdll!WinSqmIsOptedIn` at `0x1800150ff`

## pseudocode

```c
__int64 __fastcall CSqmSession::UploadThreadProc(PVOID Parameter)
{
  DWORD v1; // ebx
  __int64 v2; // r8
  unsigned int TempPath2W; // eax
  DWORD LastError; // eax
  int v5; // edx
  _QWORD *v6; // rcx
  unsigned __int16 v8[264]; // [rsp+30h] [rbp-438h] BYREF
  _BYTE v9[528]; // [rsp+240h] [rbp-228h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_6a02d0885a10324ba7005a50ff1b4315_Traceguids);
  v1 = 0;
  if ( !(unsigned int)WinSqmIsOptedIn() )
    goto LABEL_15;
  TempPath2W = GetTempPath2W(260, v9);
  v1 = TempPath2W ? (TempPath2W > 0x104 ? 0x6F : 0) : GetLastError();
  if ( v1 )
    goto LABEL_15;
  StringCchPrintfW(v8, 0x105u, L"%ws\\%ws", v9, L"ShareCPLlog*.sqm");
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_6a02d0885a10324ba7005a50ff1b4315_Traceguids, v8);
  SetLastError(0);
  LastError = GetLastError();
  v1 = LastError;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
    {
LABEL_16:
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x20) != 0 )
        WPP_SF_D(v6[2], 16, v2, v1);
      return v1;
    }
    WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, v2, (unsigned int)v8, LastError);
LABEL_15:
    v6 = WPP_GLOBAL_Control;
    goto LABEL_16;
  }
  return v1;
}

```

## disassembly

```asm
0x1800150b0  mov     [rsp+arg_0], rbx
0x1800150b5  push    rdi
0x1800150b6  sub     rsp, 460h
0x1800150bd  mov     rax, cs:__security_cookie
0x1800150c4  xor     rax, rsp
0x1800150c7  mov     [rsp+468h+var_18], rax
0x1800150cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800150d6  lea     rdi, WPP_GLOBAL_Control
0x1800150dd  cmp     rcx, rdi
0x1800150e0  jz      short loc_1800150FD
0x1800150e2  test    byte ptr [rcx+1Ch], 20h
0x1800150e6  jz      short loc_1800150FD
0x1800150e8  mov     rcx, [rcx+10h]
0x1800150ec  lea     r8, WPP_6a02d0885a10324ba7005a50ff1b4315_Traceguids
0x1800150f3  mov     edx, 0Dh
0x1800150f8  call    WPP_SF_
0x1800150fd  xor     ebx, ebx
0x1800150ff  call    cs:__imp_WinSqmIsOptedIn
0x180015105  test    eax, eax
0x180015107  jz      loc_1800151C7
0x18001510d  mov     ebx, 104h
0x180015112  lea     rdx, [rsp+468h+var_228]
0x18001511a  mov     ecx, ebx
0x18001511c  call    cs:__imp_GetTempPath2W
0x180015122  test    eax, eax
0x180015124  jz      short loc_18001512F
0x180015126  cmp     ebx, eax
0x180015128  sbb     ebx, ebx
0x18001512a  and     ebx, 6Fh
0x18001512d  jmp     short loc_180015137
0x18001512f  call    cs:__imp_GetLastError
0x180015135  mov     ebx, eax
0x180015137  test    ebx, ebx
0x180015139  jnz     loc_1800151C7
0x18001513f  lea     rax, aSharecpllogSqm; "ShareCPLlog*.sqm"
0x180015146  mov     edx, 105h; unsigned __int64
0x18001514b  lea     r9, [rsp+468h+var_228]
0x180015153  mov     [rsp+468h+var_448], rax
0x180015158  lea     r8, aWsWs; "%ws\\%ws"
0x18001515f  lea     rcx, [rsp+468h+var_438]; unsigned __int16 *
0x180015164  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180015169  mov     rcx, cs:WPP_GLOBAL_Control
0x180015170  cmp     rcx, rdi
0x180015173  jz      short loc_180015193
0x180015175  test    byte ptr [rcx+1Ch], 8
0x180015179  jz      short loc_180015193
0x18001517b  mov     rcx, [rcx+10h]
0x18001517f  lea     edx, [rbx+0Eh]
0x180015182  lea     r9, [rsp+468h+var_438]
0x180015187  lea     r8, WPP_6a02d0885a10324ba7005a50ff1b4315_Traceguids
0x18001518e  call    WPP_SF_S
0x180015193  xor     ecx, ecx; dwErrCode
0x180015195  call    cs:__imp_SetLastError
0x18001519b  call    cs:__imp_GetLastError
0x1800151a1  mov     ebx, eax
0x1800151a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800151aa  cmp     rcx, rdi
0x1800151ad  jz      short loc_1800151EA
0x1800151af  test    byte ptr [rcx+1Ch], 8
0x1800151b3  jz      short loc_1800151CE
0x1800151b5  mov     rcx, [rcx+10h]
0x1800151b9  lea     r9, [rsp+468h+var_438]
0x1800151be  mov     dword ptr [rsp+468h+var_448], eax
0x1800151c2  call    WPP_SF_SD
0x1800151c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800151ce  cmp     rcx, rdi
0x1800151d1  jz      short loc_1800151EA
0x1800151d3  test    byte ptr [rcx+1Ch], 20h
0x1800151d7  jz      short loc_1800151EA
0x1800151d9  mov     rcx, [rcx+10h]
0x1800151dd  mov     edx, 10h
0x1800151e2  mov     r9d, ebx
0x1800151e5  call    WPP_SF_D
0x1800151ea  mov     eax, ebx
0x1800151ec  mov     rcx, [rsp+468h+var_18]
0x1800151f4  xor     rcx, rsp; StackCookie
0x1800151f7  call    __security_check_cookie
0x1800151fc  mov     rbx, [rsp+468h+arg_0]
0x180015204  add     rsp, 460h
0x18001520b  pop     rdi
0x18001520c  retn
```
