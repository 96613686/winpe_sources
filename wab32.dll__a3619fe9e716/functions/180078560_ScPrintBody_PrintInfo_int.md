# ScPrintBody(_PrintInfo *,int)

- ea: `0x180078560`
- end: `0x180078767`
- name: `?ScPrintBody@@YAJPEAU_PrintInfo@@H@Z`
- size: `519`
- prototype: `__int64 __fastcall(struct _PrintInfo *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800781bc`

## callees

- `0x180077c74`
- `0x180078560`
- `0x180091ef0`

## import_xrefs

- `GDI32!SetBkMode` at `0x18007867b`
- `GDI32!SetBkMode` at `0x18007867b`
- `KERNEL32!MulDiv` at `0x18007862c`
- `KERNEL32!MulDiv` at `0x180078641`
- `KERNEL32!MulDiv` at `0x180078699`
- `KERNEL32!MulDiv` at `0x1800786ac`
- `KERNEL32!MulDiv` at `0x1800786bf`
- `KERNEL32!MulDiv` at `0x1800786d9`
- `KERNEL32!MulDiv` at `0x180078736`
- `KERNEL32!MulDiv` at `0x18007862c`
- `KERNEL32!MulDiv` at `0x180078641`
- `KERNEL32!MulDiv` at `0x180078699`
- `KERNEL32!MulDiv` at `0x1800786ac`
- `KERNEL32!MulDiv` at `0x1800786bf`
- `KERNEL32!MulDiv` at `0x1800786d9`
- `KERNEL32!MulDiv` at `0x180078736`
- `USER32!SendMessageW` at `0x180078662`
- `USER32!SendMessageW` at `0x1800786f4`
- `USER32!SendMessageW` at `0x180078662`
- `USER32!SendMessageW` at `0x1800786f4`
- `USER32!UpdateWindow` at `0x180078608`
- `USER32!UpdateWindow` at `0x180078608`
- `USER32!InvalidateRect` at `0x1800785fb`
- `USER32!InvalidateRect` at `0x1800785fb`

## pseudocode

```c
__int64 __fastcall ScPrintBody(struct _PrintInfo *a1, int a2)
{
  HWND v2; // r12
  int v3; // r15d
  unsigned int NextBand; // edi
  int v7; // r15d
  int v8; // r8d
  int v9; // ecx
  int v10; // eax
  int v11; // r8d
  int v12; // ecx
  int v13; // r12d
  int v14; // r8d
  int v15; // ecx
  int v16; // eax
  int v17; // r8d
  int v18; // ecx
  int v19; // eax
  int v20; // r8d
  int v21; // ecx
  int v22; // eax
  int v23; // ecx
  int v24; // r8d
  int v25; // eax
  int v26; // edx
  HWND hWnd; // [rsp+20h] [rbp-50h]
  HDC hdc[2]; // [rsp+28h] [rbp-48h] BYREF
  int nNumber[4]; // [rsp+38h] [rbp-38h]
  __int128 v31; // [rsp+48h] [rbp-28h]
  unsigned __int64 v32; // [rsp+58h] [rbp-18h]

  v2 = (HWND)*((_QWORD *)a1 + 20);
  v3 = a2 + *((_DWORD *)a1 + 11);
  v32 = 0;
  *(_OWORD *)hdc = 0;
  hWnd = v2;
  *(_OWORD *)nNumber = 0;
  v31 = 0;
  if ( v3 <= *((_DWORD *)a1 + 27) )
  {
    NextBand = 0;
    while ( v3 > *((_DWORD *)a1 + 13) )
    {
      NextBand = GetNextBand(a1, 1);
      if ( NextBand )
        return NextBand;
    }
    *((_DWORD *)a1 + 11) += a2 + 1;
  }
  else
  {
    NextBand = GetNextBand(a1, 1);
  }
  InvalidateRect(*((HWND *)a1 + 20), 0, 1);
  UpdateWindow(*((HWND *)a1 + 20));
  v7 = 0;
  v8 = *((_DWORD *)a1 + 6);
  v9 = *((_DWORD *)a1 + 8);
  hdc[0] = *(HDC *)a1;
  hdc[1] = 0;
  *(_QWORD *)&v31 = 0;
  v10 = MulDiv(v9, 1440, v8);
  v11 = *((_DWORD *)a1 + 7);
  v12 = *((_DWORD *)a1 + 9);
  DWORD2(v31) = v10;
  v32 = 0xFFFFFFFF00000000uLL;
  HIDWORD(v31) = MulDiv(v12, 1440, v11);
  v13 = SendMessageW(v2, 0xEu, 0, 0);
  if ( v13 > 0 )
  {
    SetBkMode(hdc[0], 1);
    do
    {
      v14 = *((_DWORD *)a1 + 7);
      v15 = *((_DWORD *)a1 + 11);
      LODWORD(v32) = v7;
      v16 = MulDiv(v15, 1440, v14);
      v17 = *((_DWORD *)a1 + 6);
      v18 = *((_DWORD *)a1 + 10);
      nNumber[1] = v16;
      v19 = MulDiv(v18, 1440, v17);
      v20 = *((_DWORD *)a1 + 6);
      v21 = *((_DWORD *)a1 + 12);
      nNumber[0] = v19;
      v22 = MulDiv(v21, 1440, v20);
      v23 = *((_DWORD *)a1 + 13);
      v24 = *((_DWORD *)a1 + 7);
      if ( v23 >= *((_DWORD *)a1 + 27) )
        v23 = *((_DWORD *)a1 + 27);
      nNumber[2] = v22;
      nNumber[3] = MulDiv(v23, 1440, v24);
      v25 = SendMessageW(hWnd, 0x439u, 1u, (LPARAM)hdc);
      v7 = v25;
      if ( v25 <= (int)v32 )
        break;
      if ( v25 <= 0 )
        break;
      if ( v25 >= v13 )
        break;
      NextBand = GetNextBand(a1, 1);
    }
    while ( !NextBand );
    v26 = *((_DWORD *)a1 + 7);
    LODWORD(v32) = HIDWORD(v32) + 1;
    *((_DWORD *)a1 + 11) = MulDiv(nNumber[3], v26, 1440);
  }
  return NextBand;
}

```

## disassembly

```asm
0x180078560  mov     [rsp-28h+arg_8], rbx
0x180078565  mov     [rsp-28h+arg_10], rdi
0x18007856a  push    rbp
0x18007856b  push    r12
0x18007856d  push    r13
0x18007856f  push    r14
0x180078571  push    r15
0x180078573  mov     rbp, rsp
0x180078576  sub     rsp, 70h
0x18007857a  mov     rax, cs:__security_cookie
0x180078581  xor     rax, rsp
0x180078584  mov     [rbp+var_10], rax
0x180078588  mov     r15d, [rcx+2Ch]
0x18007858c  xorps   xmm0, xmm0
0x18007858f  mov     r12, [rcx+0A0h]
0x180078596  xor     eax, eax
0x180078598  add     r15d, edx
0x18007859b  mov     [rbp+var_18], rax
0x18007859f  mov     r13d, edx
0x1800785a2  mov     rbx, rcx
0x1800785a5  movups  xmmword ptr [rbp+hdc], xmm0
0x1800785a9  mov     [rbp+hWnd], r12
0x1800785ad  movups  xmmword ptr [rbp+nNumber], xmm0
0x1800785b1  movups  [rbp+var_28], xmm0
0x1800785b5  cmp     r15d, [rcx+6Ch]
0x1800785b9  jle     short loc_1800785C7
0x1800785bb  lea     edx, [rax+1]; int
0x1800785be  call    ?GetNextBand@@YAJPEAU_PrintInfo@@H@Z; GetNextBand(_PrintInfo *,int)
0x1800785c3  mov     edi, eax
0x1800785c5  jmp     short loc_1800785EE
0x1800785c7  xor     edi, edi
0x1800785c9  cmp     r15d, [rbx+34h]
0x1800785cd  jle     short loc_1800785E7
0x1800785cf  mov     edx, 1; int
0x1800785d4  mov     rcx, rbx; struct _PrintInfo *
0x1800785d7  call    ?GetNextBand@@YAJPEAU_PrintInfo@@H@Z; GetNextBand(_PrintInfo *,int)
0x1800785dc  mov     edi, eax
0x1800785de  test    eax, eax
0x1800785e0  jz      short loc_1800785C9
0x1800785e2  jmp     loc_18007873F
0x1800785e7  lea     eax, [r13+1]
0x1800785eb  add     [rbx+2Ch], eax
0x1800785ee  mov     rcx, [rbx+0A0h]; hWnd
0x1800785f5  xor     edx, edx; lpRect
0x1800785f7  lea     r8d, [rdx+1]; bErase
0x1800785fb  call    cs:__imp_InvalidateRect
0x180078601  mov     rcx, [rbx+0A0h]; hWnd
0x180078608  call    cs:__imp_UpdateWindow
0x18007860e  mov     rax, [rbx]
0x180078611  xor     r15d, r15d
0x180078614  mov     r8d, [rbx+18h]; nDenominator
0x180078618  mov     edx, 5A0h; nNumerator
0x18007861d  mov     ecx, [rbx+20h]; nNumber
0x180078620  mov     [rbp+hdc], rax
0x180078624  mov     [rbp+hdc+8], r15
0x180078628  mov     qword ptr [rbp+var_28], r15
0x18007862c  call    cs:__imp_MulDiv
0x180078632  mov     r8d, [rbx+1Ch]; nDenominator
0x180078636  mov     edx, 5A0h; nNumerator
0x18007863b  mov     ecx, [rbx+24h]; nNumber
0x18007863e  mov     dword ptr [rbp+var_28+8], eax
0x180078641  call    cs:__imp_MulDiv
0x180078647  xor     r9d, r9d; lParam
0x18007864a  mov     dword ptr [rbp+var_18], r15d
0x18007864e  xor     r8d, r8d; wParam
0x180078651  mov     dword ptr [rbp+var_28+0Ch], eax
0x180078654  lea     edx, [r15+0Eh]; Msg
0x180078658  mov     dword ptr [rbp+var_18+4], 0FFFFFFFFh
0x18007865f  mov     rcx, r12; hWnd
0x180078662  call    cs:__imp_SendMessageW
0x180078668  mov     r12, rax
0x18007866b  test    eax, eax
0x18007866d  jle     loc_18007873F
0x180078673  mov     rcx, [rbp+hdc]; hdc
0x180078677  lea     edx, [r15+1]; mode
0x18007867b  call    cs:__imp_SetBkMode
0x180078681  mov     r13, [rbp+hWnd]
0x180078685  mov     r8d, [rbx+1Ch]; nDenominator
0x180078689  mov     ecx, [rbx+2Ch]; nNumber
0x18007868c  mov     dword ptr [rbp+var_18], r15d
0x180078690  mov     r15d, 5A0h
0x180078696  mov     edx, r15d; nNumerator
0x180078699  call    cs:__imp_MulDiv
0x18007869f  mov     r8d, [rbx+18h]; nDenominator
0x1800786a3  mov     edx, r15d; nNumerator
0x1800786a6  mov     ecx, [rbx+28h]; nNumber
0x1800786a9  mov     [rbp+nNumber+4], eax
0x1800786ac  call    cs:__imp_MulDiv
0x1800786b2  mov     r8d, [rbx+18h]; nDenominator
0x1800786b6  mov     edx, r15d; nNumerator
0x1800786b9  mov     ecx, [rbx+30h]; nNumber
0x1800786bc  mov     [rbp+nNumber], eax
0x1800786bf  call    cs:__imp_MulDiv
0x1800786c5  mov     ecx, [rbx+34h]
0x1800786c8  mov     edx, r15d; nNumerator
0x1800786cb  cmp     ecx, [rbx+6Ch]
0x1800786ce  mov     r8d, [rbx+1Ch]; nDenominator
0x1800786d2  cmovge  ecx, [rbx+6Ch]; nNumber
0x1800786d6  mov     [rbp+nNumber+8], eax
0x1800786d9  call    cs:__imp_MulDiv
0x1800786df  lea     r9, [rbp+hdc]; lParam
0x1800786e3  mov     edx, 439h; Msg
0x1800786e8  mov     r8d, 1; wParam
0x1800786ee  mov     [rbp+nNumber+0Ch], eax
0x1800786f1  mov     rcx, r13; hWnd
0x1800786f4  call    cs:__imp_SendMessageW
0x1800786fa  mov     r15, rax
0x1800786fd  cmp     eax, dword ptr [rbp+var_18]
0x180078700  jle     short loc_180078722
0x180078702  test    eax, eax
0x180078704  jle     short loc_180078722
0x180078706  cmp     eax, r12d
0x180078709  jge     short loc_180078722
0x18007870b  mov     edx, 1; int
0x180078710  mov     rcx, rbx; struct _PrintInfo *
0x180078713  call    ?GetNextBand@@YAJPEAU_PrintInfo@@H@Z; GetNextBand(_PrintInfo *,int)
0x180078718  mov     edi, eax
0x18007871a  test    eax, eax
0x18007871c  jz      loc_180078685
0x180078722  mov     eax, dword ptr [rbp+var_18+4]
0x180078725  mov     r8d, 5A0h; nDenominator
0x18007872b  mov     edx, [rbx+1Ch]; nNumerator
0x18007872e  inc     eax
0x180078730  mov     ecx, [rbp+nNumber+0Ch]; nNumber
0x180078733  mov     dword ptr [rbp+var_18], eax
0x180078736  call    cs:__imp_MulDiv
0x18007873c  mov     [rbx+2Ch], eax
0x18007873f  mov     eax, edi
0x180078741  mov     rcx, [rbp+var_10]
0x180078745  xor     rcx, rsp; StackCookie
0x180078748  call    __security_check_cookie
0x18007874d  lea     r11, [rsp+70h+var_s0]
0x180078752  mov     rbx, [r11+38h]
0x180078756  mov     rdi, [r11+40h]
0x18007875a  mov     rsp, r11
0x18007875d  pop     r15
0x18007875f  pop     r14
0x180078761  pop     r13
0x180078763  pop     r12
0x180078765  pop     rbp
0x180078766  retn
```
