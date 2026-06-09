# HrGetEventingManager(char *,IUPnPEventingManager * *)

- ea: `0x1800080bc`
- end: `0x18000833d`
- name: `?HrGetEventingManager@@YAJPEADPEAPEAUIUPnPEventingManager@@@Z`
- size: `641`
- prototype: `__int64 __fastcall(char *, struct IUPnPEventingManager **)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006f64`
- `0x180007310`
- `0x180007734`

## callees

- `0x180001400`
- `0x180002504`
- `0x1800038ec`
- `0x1800080bc`
- `0x180009a74`
- `0x18000c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800082d3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800082dc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800082d3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800082dc`
- `api-ms-win-crt-private-l1-1-0!_o_strtok` at `0x18000819b`
- `api-ms-win-crt-private-l1-1-0!_o_strtok` at `0x1800081c7`
- `api-ms-win-crt-private-l1-1-0!_o_strtok` at `0x18000819b`
- `api-ms-win-crt-private-l1-1-0!_o_strtok` at `0x1800081c7`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x180008110`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x180008110`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000820d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000820d`

## pseudocode

```c
__int64 __fastcall HrGetEventingManager(char *a1, struct IUPnPEventingManager **a2)
{
  unsigned __int16 *v3; // r15
  unsigned __int16 *v4; // r14
  char *v5; // r9
  char *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rax
  char *v9; // rbp
  char *v10; // rax
  char *v11; // rax
  HRESULT v12; // ebx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  char *v15; // r9
  LPVOID ppv; // [rsp+30h] [rbp-48h] BYREF
  char SubStr[8]; // [rsp+38h] [rbp-40h] BYREF

  strcpy(SubStr, "event=");
  v3 = 0;
  v4 = 0;
  v5 = strstr(a1, SubStr);
  if ( !v5 )
  {
    v12 = -2147024809;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
      goto LABEL_26;
    v14 = 15;
    v15 = 0;
LABEL_25:
    WPP_SF_s(v13[2], v14, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids, v15);
    goto LABEL_26;
  }
  v6 = SubStr;
  v7 = 0x7FFFFFFF;
  do
  {
    if ( !*v6 )
      break;
    ++v6;
    --v7;
  }
  while ( v7 );
  v8 = (0x7FFFFFFF - v7) & -(__int64)(v7 != 0);
  v9 = &v5[v8];
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids, &v5[v8]);
  v10 = strtok(v9, "+");
  if ( !v10 )
  {
    v12 = -2147024809;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
      goto LABEL_26;
    v14 = 17;
    goto LABEL_18;
  }
  v3 = WszFromSz(v10);
  if ( !v3 )
  {
LABEL_14:
    v12 = -2147024882;
    goto LABEL_26;
  }
  v11 = strtok(0, "+");
  if ( !v11 )
  {
    v12 = -2147024809;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
      goto LABEL_26;
    v14 = 16;
LABEL_18:
    v15 = v9;
    goto LABEL_25;
  }
  v4 = WszFromSz(v11);
  if ( !v4 )
    goto LABEL_14;
  ppv = 0;
  v12 = CoCreateInstance(&CLSID_UPnPRegistrar, 0, 1u, &IID_IUPnPRegistrarLookup, &ppv);
  if ( v12 >= 0 )
  {
    v12 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, unsigned __int16 *, struct IUPnPEventingManager **))(*(_QWORD *)ppv + 24LL))(
            ppv,
            v3,
            v4,
            a2);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
LABEL_26:
  free(v3);
  free(v4);
  if ( v12 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      (unsigned int)WPP_604df09e42be3037ea2c3a056a88862f_Traceguids,
      (unsigned int)"HrGetEventingManager",
      v12);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800080bc  mov     [rsp+arg_10], rbx
0x1800080c1  mov     [rsp+arg_18], rbp
0x1800080c6  push    rsi
0x1800080c7  push    r12
0x1800080c9  push    r13
0x1800080cb  push    r14
0x1800080cd  push    r15
0x1800080cf  sub     rsp, 50h
0x1800080d3  mov     rax, cs:__security_cookie
0x1800080da  xor     rax, rsp
0x1800080dd  mov     [rsp+78h+var_38], rax
0x1800080e2  mov     eax, dword ptr cs:aEvent; "event="
0x1800080e8  mov     r12, rdx
0x1800080eb  mov     dword ptr [rsp+78h+SubStr], eax
0x1800080ef  lea     rdx, [rsp+78h+SubStr]; SubStr
0x1800080f4  movzx   eax, word ptr cs:aEvent+4; "t="
0x1800080fb  xor     r15d, r15d
0x1800080fe  mov     [rsp+78h+var_3C], ax
0x180008103  xor     r14d, r14d
0x180008106  mov     al, byte ptr cs:aEvent+6; ""
0x18000810c  mov     [rsp+78h+var_3A], al
0x180008110  call    cs:__imp_strstr
0x180008116  lea     r13, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids
0x18000811d  mov     r9, rax
0x180008120  test    rax, rax
0x180008123  jz      loc_18000829B
0x180008129  mov     r8d, 7FFFFFFFh
0x18000812f  lea     rax, [rsp+78h+SubStr]
0x180008134  mov     edx, r8d
0x180008137  cmp     [rax], r14b
0x18000813a  jz      short loc_180008145
0x18000813c  inc     rax
0x18000813f  sub     rdx, 1
0x180008143  jnz     short loc_180008137
0x180008145  sub     r8, rdx
0x180008148  mov     rax, rdx
0x18000814b  neg     rax
0x18000814e  sbb     rcx, rcx
0x180008151  and     rcx, r8
0x180008154  neg     rdx
0x180008157  sbb     rax, rax
0x18000815a  and     rax, rcx
0x18000815d  lea     rbp, [rax+r9]
0x180008161  mov     rcx, cs:WPP_GLOBAL_Control
0x180008168  lea     rsi, WPP_GLOBAL_Control
0x18000816f  cmp     rcx, rsi
0x180008172  jz      short loc_180008191
0x180008174  test    dword ptr [rcx+1Ch], 800h
0x18000817b  jz      short loc_180008191
0x18000817d  mov     rcx, [rcx+10h]
0x180008181  mov     edx, 0Eh
0x180008186  mov     r9, rbp
0x180008189  mov     r8, r13
0x18000818c  call    WPP_SF_s
0x180008191  lea     rdx, Delimiter; "+"
0x180008198  mov     rcx, rbp; String
0x18000819b  call    cs:__imp_strtok
0x1800081a1  test    rax, rax
0x1800081a4  jz      loc_18000827A
0x1800081aa  mov     rcx, rax; lpMultiByteStr
0x1800081ad  call    ?WszFromSz@@YAPEAGPEBD@Z; WszFromSz(char const *)
0x1800081b2  mov     r15, rax
0x1800081b5  test    rax, rax
0x1800081b8  jz      loc_18000824F
0x1800081be  lea     rdx, Delimiter; "+"
0x1800081c5  xor     ecx, ecx; String
0x1800081c7  call    cs:__imp_strtok
0x1800081cd  test    rax, rax
0x1800081d0  jz      loc_180008256
0x1800081d6  mov     rcx, rax; lpMultiByteStr
0x1800081d9  call    ?WszFromSz@@YAPEAGPEBD@Z; WszFromSz(char const *)
0x1800081de  mov     r14, rax
0x1800081e1  test    rax, rax
0x1800081e4  jz      short loc_18000824F
0x1800081e6  xor     edx, edx; pUnkOuter
0x1800081e8  mov     [rsp+78h+var_48], 0
0x1800081f1  lea     rax, [rsp+78h+var_48]
0x1800081f6  lea     r9, IID_IUPnPRegistrarLookup; riid
0x1800081fd  mov     [rsp+78h+ppv], rax; ppv
0x180008202  lea     rcx, CLSID_UPnPRegistrar; rclsid
0x180008209  lea     r8d, [rdx+1]; dwClsContext
0x18000820d  call    cs:__imp_CoCreateInstance
0x180008213  mov     ebx, eax
0x180008215  test    eax, eax
0x180008217  js      loc_1800082D0
0x18000821d  mov     rcx, [rsp+78h+var_48]
0x180008222  mov     r9, r12
0x180008225  mov     r8, r14
0x180008228  mov     rdx, r15
0x18000822b  mov     rax, [rcx]
0x18000822e  mov     rax, [rax+18h]
0x180008232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008237  mov     rcx, [rsp+78h+var_48]
0x18000823c  mov     ebx, eax
0x18000823e  mov     rax, [rcx]
0x180008241  mov     rax, [rax+10h]
0x180008245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000824a  jmp     loc_1800082D0
0x18000824f  mov     ebx, 8007000Eh
0x180008254  jmp     short loc_1800082D0
0x180008256  mov     ebx, 80070057h
0x18000825b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008262  cmp     rcx, rsi
0x180008265  jz      short loc_1800082D0
0x180008267  test    dword ptr [rcx+1Ch], 800h
0x18000826e  jz      short loc_1800082D0
0x180008270  mov     edx, 10h
0x180008275  mov     r9, rbp
0x180008278  jmp     short loc_1800082C4
0x18000827a  mov     ebx, 80070057h
0x18000827f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008286  cmp     rcx, rsi
0x180008289  jz      short loc_1800082D0
0x18000828b  test    dword ptr [rcx+1Ch], 800h
0x180008292  jz      short loc_1800082D0
0x180008294  mov     edx, 11h
0x180008299  jmp     short loc_180008275
0x18000829b  mov     ebx, 80070057h
0x1800082a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800082a7  lea     rsi, WPP_GLOBAL_Control
0x1800082ae  cmp     rcx, rsi
0x1800082b1  jz      short loc_1800082D0
0x1800082b3  test    dword ptr [rcx+1Ch], 800h
0x1800082ba  jz      short loc_1800082D0
0x1800082bc  mov     edx, 0Fh
0x1800082c1  xor     r9d, r9d
0x1800082c4  mov     rcx, [rcx+10h]
0x1800082c8  mov     r8, r13
0x1800082cb  call    WPP_SF_s
0x1800082d0  mov     rcx, r15; Block
0x1800082d3  call    cs:__imp_free
0x1800082d9  mov     rcx, r14; Block
0x1800082dc  call    cs:__imp_free
0x1800082e2  test    ebx, ebx
0x1800082e4  jz      short loc_180008314
0x1800082e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800082ed  cmp     rcx, rsi
0x1800082f0  jz      short loc_180008314
0x1800082f2  test    byte ptr [rcx+1Ch], 1
0x1800082f6  jz      short loc_180008314
0x1800082f8  mov     rcx, [rcx+10h]
0x1800082fc  lea     r9, aHrgeteventingm; "HrGetEventingManager"
0x180008303  mov     edx, 12h
0x180008308  mov     dword ptr [rsp+78h+ppv], ebx
0x18000830c  mov     r8, r13
0x18000830f  call    WPP_SF_sd
0x180008314  mov     eax, ebx
0x180008316  mov     rcx, [rsp+78h+var_38]
0x18000831b  xor     rcx, rsp; StackCookie
0x18000831e  call    __security_check_cookie
0x180008323  lea     r11, [rsp+78h+var_28]
0x180008328  mov     rbx, [r11+40h]
0x18000832c  mov     rbp, [r11+48h]
0x180008330  mov     rsp, r11
0x180008333  pop     r15
0x180008335  pop     r14
0x180008337  pop     r13
0x180008339  pop     r12
0x18000833b  pop     rsi
0x18000833c  retn
```
