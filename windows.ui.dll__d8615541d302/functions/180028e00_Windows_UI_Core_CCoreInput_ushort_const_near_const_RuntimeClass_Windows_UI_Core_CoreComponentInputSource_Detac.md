# Windows::UI::Core::CCoreInput<&ushort const near * const RuntimeClass_Windows_UI_Core_CoreComponentInputSource>::DetachInputHandle(void * *)

- ea: `0x180028e00`
- end: `0x180029093`
- name: `?DetachInputHandle@?$CCoreInput@$1?RuntimeClass_Windows_UI_Core_CoreComponentInputSource@@3QBGB@Core@UI@Windows@@UEAAJPEAPEAX@Z`
- size: `659`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180028e00`
- `0x180029120`
- `0x180029134`
- `0x180061b1c`
- `0x1800c73c0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002903b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002903b`
- `dcomp!__imp_NtCreateCompositionInputSink` at `0x180029023`
- `dcomp!__imp_NtCreateCompositionInputSink` at `0x180029023`
- `ext-ms-win-rtcore-minuser-input-l1-1-1!GetRoutingInfoForWindowHandle` at `0x180028ecc`
- `ext-ms-win-rtcore-minuser-input-l1-1-1!GetRoutingInfoForWindowHandle` at `0x180028ecc`

## pseudocode

```c
__int64 __fastcall Windows::UI::Core::CCoreInput<&unsigned short const near * const RuntimeClass_Windows_UI_Core_CoreComponentInputSource>::DetachInputHandle(
        __int64 a1,
        HANDLE *a2)
{
  int v4; // ebx
  HANDLE *v5; // rdi
  CoreInputSink *v6; // rcx
  __int64 v7; // r14
  int v8; // eax
  bool v9; // zf
  __int128 v10; // xmm3
  __int128 v11; // xmm4
  __int64 v12; // xmm5_8
  int v13; // eax
  __int128 v14; // xmm2
  __int128 v15; // xmm7
  __int128 v16; // xmm8
  __int128 v17; // xmm9
  __int64 v18; // xmm10_8
  __int128 v19; // xmm7
  __int128 v20; // xmm8
  __int128 v21; // xmm9
  __int64 v22; // xmm10_8
  __int128 v23; // xmm7
  __int128 v24; // xmm8
  __int128 v25; // xmm9
  __int64 v26; // xmm10_8
  int v27; // eax
  unsigned __int64 v29; // [rsp+28h] [rbp-E0h]
  __int128 v30; // [rsp+60h] [rbp-A8h]
  __int128 v31; // [rsp+98h] [rbp-70h] BYREF
  __int128 v32; // [rsp+A8h] [rbp-60h]
  __int64 v33; // [rsp+B8h] [rbp-50h]
  __int64 v34; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v35; // [rsp+D0h] [rbp-38h]
  __int128 v36; // [rsp+E0h] [rbp-28h]
  __int128 v37; // [rsp+F0h] [rbp-18h]
  __int64 v38; // [rsp+100h] [rbp-8h]
  __int128 v39; // [rsp+108h] [rbp+0h]
  __int128 v40; // [rsp+118h] [rbp+10h]
  __int128 v41; // [rsp+128h] [rbp+20h]
  __int64 v42; // [rsp+138h] [rbp+30h]
  __int128 v43; // [rsp+140h] [rbp+38h]
  __int128 v44; // [rsp+150h] [rbp+48h]
  __int128 v45; // [rsp+160h] [rbp+58h]
  __int64 v46; // [rsp+170h] [rbp+68h]
  __int128 v47; // [rsp+178h] [rbp+70h]
  __int128 v48; // [rsp+188h] [rbp+80h]
  __int128 v49; // [rsp+198h] [rbp+90h]
  __int64 v50; // [rsp+1A8h] [rbp+A0h]
  __int64 v51; // [rsp+1B0h] [rbp+A8h]
  __int64 v52; // [rsp+1B8h] [rbp+B0h]
  __int128 v53; // [rsp+1C0h] [rbp+B8h]
  __int128 v54; // [rsp+1D0h] [rbp+C8h]
  __int64 v55; // [rsp+1E0h] [rbp+D8h]
  __int64 v56; // [rsp+1E8h] [rbp+E0h]

  *a2 = 0;
  if ( *(_QWORD *)(a1 + 1192) )
  {
    v5 = (HANDLE *)(a1 + 1208);
    if ( CoreInputSink::Handle((CoreInputSink *)(a1 + 1216)) )
      *v5 = CoreInputSink::Detach(v6);
    v4 = 0;
    if ( *v5 )
      goto LABEL_25;
    v7 = *(_QWORD *)(a1 + 1192);
    v8 = 0;
    DWORD1(v30) = 0;
    HIDWORD(v29) = 0;
    v33 = 0;
    v31 = 0;
    v32 = 0;
    if ( v7 )
    {
      if ( !(unsigned __int8)IsGetRoutingInfoForWindowHandlePresent()
        || (v9 = (unsigned int)GetRoutingInfoForWindowHandle(v7, &v31) == 0, v8 = 3, v9) )
      {
        v8 = 2;
      }
    }
    v10 = v31;
    LODWORD(v30) = v8;
    v11 = v32;
    LODWORD(v29) = 0;
    v12 = v33;
    v56 = 0;
    v13 = *(_DWORD *)(a1 + 1204);
    *((_QWORD *)&v30 + 1) = v7;
    v34 = 296;
    v14 = v30;
    if ( (v13 & 4) != 0 )
    {
      v15 = v30;
      v16 = v31;
      v17 = v32;
      v18 = v33;
    }
    else
    {
      v15 = v29;
      v16 = 0;
      v17 = 0;
      v18 = 0;
    }
    v38 = v18;
    v35 = v15;
    v36 = v16;
    v37 = v17;
    if ( (v13 & 8) != 0 )
    {
      v19 = v30;
      v20 = v31;
      v21 = v32;
      v22 = v33;
    }
    else
    {
      v19 = v29;
      v20 = 0;
      v21 = 0;
      v22 = 0;
    }
    v39 = v19;
    v40 = v20;
    v41 = v21;
    v42 = v22;
    if ( (v13 & 1) != 0 )
    {
      v23 = v30;
      v24 = v31;
      v25 = v32;
      v26 = v33;
    }
    else
    {
      v23 = v29;
      v24 = 0;
      v25 = 0;
      v26 = 0;
    }
    v46 = v26;
    v43 = v23;
    v44 = v24;
    v45 = v25;
    if ( (v13 & 2) == 0 )
    {
      v14 = v29;
      v10 = 0;
      v11 = 0;
      v12 = 0;
    }
    v47 = v14;
    v48 = v10;
    v49 = v11;
    v50 = v12;
    v51 = 0;
    v52 = 0;
    v53 = 0;
    v54 = 0;
    v55 = 0;
    v27 = NtCreateCompositionInputSink(&v34, a1 + 1208);
    v4 = v27 | 0x10000000;
    if ( v27 >= 0 )
      goto LABEL_25;
  }
  else
  {
    v4 = -2147467259;
    v5 = (HANDLE *)(a1 + 1208);
  }
  if ( *v5 )
  {
    CloseHandle(*v5);
    *v5 = 0;
  }
  if ( v4 >= 0 )
LABEL_25:
    *a2 = *v5;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180028e00  mov     rax, rsp
0x180028e03  mov     [rax+18h], rbx
0x180028e07  push    rbp
0x180028e08  push    rsi
0x180028e09  push    rdi
0x180028e0a  push    r14
0x180028e0c  push    r15
0x180028e0e  lea     rbp, [rax-178h]
0x180028e15  sub     rsp, 250h
0x180028e1c  movaps  xmmword ptr [rax-38h], xmm6
0x180028e20  movaps  xmmword ptr [rax-48h], xmm7
0x180028e24  movaps  xmmword ptr [rax-58h], xmm8
0x180028e29  movaps  xmmword ptr [rax-68h], xmm9
0x180028e2e  movaps  xmmword ptr [rax-78h], xmm10
0x180028e33  mov     rax, cs:__security_cookie
0x180028e3a  xor     rax, rsp
0x180028e3d  mov     [rbp+170h+var_80], rax
0x180028e44  mov     qword ptr [rdx], 0
0x180028e4b  mov     r15, rdx
0x180028e4e  cmp     qword ptr [rcx+4A8h], 0
0x180028e56  mov     rsi, rcx
0x180028e59  jnz     short loc_180028E6C
0x180028e5b  mov     ebx, 80004005h
0x180028e60  lea     rdi, [rcx+4B8h]
0x180028e67  jmp     loc_180029033
0x180028e6c  add     rcx, 4C0h; this
0x180028e73  call    ?Handle@CoreInputSink@@QEAAPEAXXZ; CoreInputSink::Handle(void)
0x180028e78  lea     rdi, [rsi+4B8h]
0x180028e7f  test    rax, rax
0x180028e82  jz      short loc_180028E8C
0x180028e84  call    ?Detach@CoreInputSink@@QEAAPEAXXZ; CoreInputSink::Detach(void)
0x180028e89  mov     [rdi], rax
0x180028e8c  xor     ebx, ebx
0x180028e8e  cmp     [rdi], rbx
0x180028e91  jnz     loc_18002904C
0x180028e97  mov     r14, [rsi+4A8h]
0x180028e9e  xor     eax, eax
0x180028ea0  mov     dword ptr [rsp+270h+var_220+0Ch], ebx
0x180028ea4  xorps   xmm0, xmm0
0x180028ea7  mov     dword ptr [rsp+270h+var_258+0Ch], ebx
0x180028eab  mov     [rbp+170h+var_1C0], rax
0x180028eaf  movups  [rbp+170h+var_1E0], xmm0
0x180028eb3  movups  [rbp+170h+var_1D0], xmm0
0x180028eb7  test    r14, r14
0x180028eba  jz      short loc_180028EDE
0x180028ebc  call    IsGetRoutingInfoForWindowHandlePresent
0x180028ec1  test    al, al
0x180028ec3  jz      short loc_180028ED9
0x180028ec5  lea     rdx, [rbp+170h+var_1E0]
0x180028ec9  mov     rcx, r14
0x180028ecc  call    cs:__imp_GetRoutingInfoForWindowHandle
0x180028ed2  test    eax, eax
0x180028ed4  lea     eax, [rbx+3]
0x180028ed7  jnz     short loc_180028EDE
0x180028ed9  mov     eax, 2
0x180028ede  movups  xmm3, [rbp+170h+var_1E0]
0x180028ee2  mov     dword ptr [rsp+270h+var_220+8], eax
0x180028ee6  xor     eax, eax
0x180028ee8  movups  xmm4, [rbp+170h+var_1D0]
0x180028eec  mov     dword ptr [rsp+270h+var_258+8], eax
0x180028ef0  movsd   xmm5, [rbp+170h+var_1C0]
0x180028ef5  xorps   xmm0, xmm0
0x180028ef8  mov     [rsp+270h+var_248], rax
0x180028efd  movq    xmm1, rax
0x180028f02  movups  xmm6, [rsp+270h+var_258+8]
0x180028f07  mov     [rbp+170h+var_90], rax
0x180028f0e  mov     eax, [rsi+4B4h]
0x180028f14  mov     [rsp+270h+var_210], r14
0x180028f19  mov     [rbp+170h+var_1B0], 128h
0x180028f21  movups  xmm2, [rsp+270h+var_220+8]
0x180028f26  test    al, 4
0x180028f28  jz      short loc_180028F3B
0x180028f2a  movups  xmm7, xmm2
0x180028f2d  movups  xmm8, xmm3
0x180028f31  movups  xmm9, xmm4
0x180028f35  movaps  xmm10, xmm5
0x180028f39  jmp     short loc_180028F4A
0x180028f3b  movups  xmm7, xmm6
0x180028f3e  xorps   xmm8, xmm8
0x180028f42  xorps   xmm9, xmm9
0x180028f46  movaps  xmm10, xmm1
0x180028f4a  movsd   [rbp+170h+var_178], xmm10
0x180028f50  movups  [rbp+170h+var_1A8], xmm7
0x180028f54  movups  [rbp+170h+var_198], xmm8
0x180028f59  movups  [rbp+170h+var_188], xmm9
0x180028f5e  test    al, 8
0x180028f60  jz      short loc_180028F73
0x180028f62  movups  xmm7, xmm2
0x180028f65  movups  xmm8, xmm3
0x180028f69  movups  xmm9, xmm4
0x180028f6d  movaps  xmm10, xmm5
0x180028f71  jmp     short loc_180028F82
0x180028f73  movups  xmm7, xmm6
0x180028f76  xorps   xmm8, xmm8
0x180028f7a  xorps   xmm9, xmm9
0x180028f7e  movaps  xmm10, xmm1
0x180028f82  movaps  [rbp+170h+var_170], xmm7
0x180028f86  movaps  [rbp+170h+var_160], xmm8
0x180028f8b  movaps  [rbp+170h+var_150], xmm9
0x180028f90  movsd   [rbp+170h+var_140], xmm10
0x180028f96  test    al, 1
0x180028f98  jz      short loc_180028FAB
0x180028f9a  movups  xmm7, xmm2
0x180028f9d  movups  xmm8, xmm3
0x180028fa1  movups  xmm9, xmm4
0x180028fa5  movaps  xmm10, xmm5
0x180028fa9  jmp     short loc_180028FBA
0x180028fab  movups  xmm7, xmm6
0x180028fae  xorps   xmm8, xmm8
0x180028fb2  xorps   xmm9, xmm9
0x180028fb6  movaps  xmm10, xmm1
0x180028fba  movsd   [rbp+170h+var_108], xmm10
0x180028fc0  movups  [rbp+170h+var_138], xmm7
0x180028fc4  movups  [rbp+170h+var_128], xmm8
0x180028fc9  movups  [rbp+170h+var_118], xmm9
0x180028fce  test    al, 2
0x180028fd0  jnz     short loc_180028FDE
0x180028fd2  movups  xmm2, xmm6
0x180028fd5  xorps   xmm3, xmm3
0x180028fd8  xorps   xmm4, xmm4
0x180028fdb  movaps  xmm5, xmm1
0x180028fde  mov     rdx, rdi
0x180028fe1  movaps  [rbp+170h+var_100], xmm2
0x180028fe5  lea     rcx, [rbp+170h+var_1B0]
0x180028fe9  movaps  [rbp+170h+var_F0], xmm3
0x180028ff0  movaps  [rbp+170h+var_E0], xmm4
0x180028ff7  movsd   [rbp+170h+var_D0], xmm5
0x180028fff  mov     [rbp+170h+var_C8], rbx
0x180029006  mov     [rbp+170h+var_C0], rbx
0x18002900d  movups  [rbp+170h+var_B8], xmm0
0x180029014  movups  [rbp+170h+var_A8], xmm0
0x18002901b  movsd   [rbp+170h+var_98], xmm1
0x180029023  call    cs:__imp_NtCreateCompositionInputSink
0x180029029  mov     ebx, eax
0x18002902b  or      ebx, 10000000h
0x180029031  jge     short loc_18002904C
0x180029033  mov     rcx, [rdi]; hObject
0x180029036  test    rcx, rcx
0x180029039  jz      short loc_180029048
0x18002903b  call    cs:__imp_CloseHandle
0x180029041  mov     qword ptr [rdi], 0
0x180029048  test    ebx, ebx
0x18002904a  js      short loc_180029052
0x18002904c  mov     rcx, [rdi]
0x18002904f  mov     [r15], rcx
0x180029052  mov     eax, ebx
0x180029054  mov     rcx, [rbp+170h+var_80]
0x18002905b  xor     rcx, rsp; StackCookie
0x18002905e  call    __security_check_cookie
0x180029063  lea     r11, [rsp+270h+var_20]
0x18002906b  mov     rbx, [r11+40h]
0x18002906f  movaps  xmm6, xmmword ptr [r11-10h]
0x180029074  movaps  xmm7, xmmword ptr [r11-20h]
0x180029079  movaps  xmm8, xmmword ptr [r11-30h]
0x18002907e  movaps  xmm9, xmmword ptr [r11-40h]
0x180029083  movaps  xmm10, xmmword ptr [r11-50h]
0x180029088  mov     rsp, r11
0x18002908b  pop     r15
0x18002908d  pop     r14
0x18002908f  pop     rdi
0x180029090  pop     rsi
0x180029091  pop     rbp
0x180029092  retn
```
