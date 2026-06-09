# CdcBuildCompatibleIDs

- ea: `0x140022590`
- end: `0x140022809`
- name: `CdcBuildCompatibleIDs`
- size: `633`
- prototype: `__int64 __usercall@<rax>(NTSTRSAFE_PWSTR pszDest@<rcx>, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140026e14`

## callees

- `0x14000f83c`
- `0x140022590`

## pseudocode

```c
__int64 __fastcall CdcBuildCompatibleIDs(NTSTRSAFE_PWSTR pszDest, __int64 a2, _WORD *a3, unsigned __int8 *a4, int a5)
{
  int v5; // ebx
  NTSTATUS v8; // eax
  unsigned int v9; // ecx
  NTSTRSAFE_PWSTR v10; // r10
  size_t v11; // rdx
  wchar_t *v12; // r10
  NTSTRSAFE_PWSTR v13; // r10
  size_t v14; // rdx
  NTSTATUS v15; // eax
  size_t v16; // rdx
  wchar_t *v17; // r10
  int v18; // ebx
  int v19; // ebx
  NTSTRSAFE_PWSTR v20; // r10
  size_t v21; // rdx
  __int64 v23; // [rsp+30h] [rbp-30h]
  __int64 v24; // [rsp+38h] [rbp-28h]
  size_t pcbRemaining[2]; // [rsp+50h] [rbp-10h] BYREF
  NTSTRSAFE_PWSTR ppszDestEnd; // [rsp+80h] [rbp+20h] BYREF

  v5 = a5;
  pcbRemaining[0] = 1024;
  ppszDestEnd = pszDest;
  switch ( a5 )
  {
    case 0:
      return (unsigned int)-1073741595;
    case 1:
    case 2:
      v8 = RtlStringCbPrintfExW(
             pszDest,
             0x400u,
             &ppszDestEnd,
             pcbRemaining,
             0,
             L"USB\\Class_%02x&SubClass_%02x&Prot_%02x",
             a4[5],
             a4[6],
             a4[7]);
      break;
    case 3:
      v8 = RtlStringCbPrintfExW(
             pszDest,
             0x400u,
             &ppszDestEnd,
             pcbRemaining,
             0,
             L"USB\\Class_%02x&SubClass_Modem&Prot_%02x",
             a4[5],
             a4[7]);
      break;
    case 4:
      v8 = RtlStringCbPrintfExW(pszDest, 0x400u, &ppszDestEnd, pcbRemaining, 0, L"USB\\Class_%02x&WPD_OBEX", a4[5]);
      break;
    default:
      return (unsigned int)-1073741595;
  }
  v9 = v8;
  if ( v8 < 0 )
    return v9;
  if ( pcbRemaining[0] <= 2 )
    return (unsigned int)-2147483643;
  v10 = ppszDestEnd;
  v11 = pcbRemaining[0] - 2;
  pcbRemaining[0] -= 2LL;
  *ppszDestEnd = 0;
  v12 = v10 + 1;
  ppszDestEnd = v12;
  if ( v5 == 1 || v5 == 2 )
  {
    LODWORD(v24) = a4[6];
    LODWORD(v23) = a4[5];
    v15 = RtlStringCbPrintfExW(v12, v11, &ppszDestEnd, pcbRemaining, 0, L"USB\\Class_%02x&SubClass_%02x", v23, v24);
    goto LABEL_17;
  }
  if ( v5 == 3 )
  {
    LODWORD(v23) = a4[5];
    v15 = RtlStringCbPrintfExW(v12, v11, &ppszDestEnd, pcbRemaining, 0, L"USB\\Class_%02x&SubClass_Modem", v23);
LABEL_17:
    v9 = v15;
    if ( v15 < 0 )
      return v9;
    v13 = ppszDestEnd;
    v14 = pcbRemaining[0];
    goto LABEL_19;
  }
  v13 = v12 - 1;
  v14 = v11 + 2;
LABEL_19:
  if ( v14 <= 2 )
    return (unsigned int)-2147483643;
  v16 = v14 - 2;
  *v13 = 0;
  v17 = v13 + 1;
  ppszDestEnd = v17;
  pcbRemaining[0] = v16;
  v18 = v5 - 1;
  if ( v18 )
  {
    v19 = v18 - 1;
    if ( v19 )
    {
      if ( (unsigned int)(v19 - 1) >= 2 )
      {
        v20 = v17 - 1;
        v21 = v16 + 2;
        goto LABEL_26;
      }
    }
  }
  LODWORD(v23) = a4[5];
  v9 = RtlStringCbPrintfExW(v17, v16, &ppszDestEnd, pcbRemaining, 0, L"USB\\Class_%02x", v23);
  if ( (v9 & 0x80000000) == 0 )
  {
    v20 = ppszDestEnd;
    v21 = pcbRemaining[0];
LABEL_26:
    if ( v21 > 4 )
    {
      *(_DWORD *)v20 = 0;
      *a3 = 1024 - (v21 - 4);
      return v9;
    }
    return (unsigned int)-2147483643;
  }
  return v9;
}

```

## disassembly

```asm
0x140022590  mov     r11, rsp
0x140022593  mov     [r11+10h], rbx
0x140022597  mov     [r11+18h], rsi
0x14002259b  push    rbp
0x14002259c  push    rdi
0x14002259d  push    r14
0x14002259f  mov     rbp, rsp
0x1400225a2  sub     rsp, 60h
0x1400225a6  mov     ebx, [rbp+arg_20]
0x1400225a9  mov     edi, 400h
0x1400225ae  mov     [rbp+pcbRemaining], rdi
0x1400225b2  mov     rsi, r9
0x1400225b5  mov     [rbp+ppszDestEnd], rcx
0x1400225b9  mov     r14, r8
0x1400225bc  mov     r10, rcx
0x1400225bf  mov     edx, ebx
0x1400225c1  test    ebx, ebx
0x1400225c3  jz      loc_1400227EC
0x1400225c9  sub     edx, 1
0x1400225cc  jz      short loc_14002264A
0x1400225ce  sub     edx, 1
0x1400225d1  jz      short loc_14002264A
0x1400225d3  sub     edx, 1
0x1400225d6  jz      short loc_14002260E
0x1400225d8  cmp     edx, 1
0x1400225db  jnz     loc_1400227EC
0x1400225e1  movzx   eax, byte ptr [r9+5]
0x1400225e6  lea     r8, [rbp+ppszDestEnd]; ppszDestEnd
0x1400225ea  mov     dword ptr [rsp+60h+var_30], eax
0x1400225ee  lea     r9, [rbp+pcbRemaining]; pcbRemaining
0x1400225f2  lea     rax, aUsbClass02xWpd; "USB\\Class_%02x&WPD_OBEX"
0x1400225f9  mov     edx, edi; cbDest
0x1400225fb  mov     [r11-50h], rax
0x1400225ff  mov     qword ptr [r11-58h], 0
0x140022607  call    RtlStringCbPrintfExW
0x14002260c  jmp     short loc_14002268D
0x14002260e  movzx   eax, byte ptr [r9+7]
0x140022613  lea     r8, [rbp+ppszDestEnd]; ppszDestEnd
0x140022617  movzx   ecx, byte ptr [r9+5]
0x14002261c  mov     rdx, rdi; cbDest
0x14002261f  mov     dword ptr [rsp+60h+var_28], eax
0x140022623  lea     r9, [rbp+pcbRemaining]; pcbRemaining
0x140022627  mov     dword ptr [rsp+60h+var_30], ecx
0x14002262b  lea     rax, aUsbClass02xSub_1; "USB\\Class_%02x&SubClass_Modem&Prot_%02"...
0x140022632  mov     [rsp+60h+pszFormat], rax; pszFormat
0x140022637  mov     rcx, r10; pszDest
0x14002263a  mov     qword ptr [rsp+60h+dwFlags], 0; dwFlags
0x140022643  call    RtlStringCbPrintfExW
0x140022648  jmp     short loc_14002268D
0x14002264a  movzx   eax, byte ptr [r9+7]
0x14002264f  lea     r8, [rbp+ppszDestEnd]; ppszDestEnd
0x140022653  movzx   ecx, byte ptr [r9+6]
0x140022658  movzx   edx, byte ptr [r9+5]
0x14002265d  lea     r9, [rbp+pcbRemaining]; pcbRemaining
0x140022661  mov     [rsp+60h+var_20], eax
0x140022665  lea     rax, aUsbClass02xSub_3; "USB\\Class_%02x&SubClass_%02x&Prot_%02x"
0x14002266c  mov     dword ptr [rsp+60h+var_28], ecx
0x140022670  mov     rcx, r10; pszDest
0x140022673  mov     dword ptr [rsp+60h+var_30], edx
0x140022677  mov     rdx, rdi; cbDest
0x14002267a  mov     [rsp+60h+pszFormat], rax; pszFormat
0x14002267f  mov     qword ptr [rsp+60h+dwFlags], 0; dwFlags
0x140022688  call    RtlStringCbPrintfExW
0x14002268d  mov     ecx, eax
0x14002268f  test    eax, eax
0x140022691  js      loc_1400227F1
0x140022697  mov     rdx, [rbp+pcbRemaining]
0x14002269b  cmp     rdx, 2
0x14002269f  jbe     loc_1400227E5
0x1400226a5  mov     r10, [rbp+ppszDestEnd]
0x1400226a9  xor     eax, eax
0x1400226ab  sub     rdx, 2; cbDest
0x1400226af  mov     r8d, ebx
0x1400226b2  mov     [rbp+pcbRemaining], rdx
0x1400226b6  mov     [r10], ax
0x1400226ba  add     r10, 2
0x1400226be  mov     [rbp+ppszDestEnd], r10
0x1400226c2  sub     r8d, 1
0x1400226c6  jz      short loc_14002270D
0x1400226c8  sub     r8d, 1
0x1400226cc  jz      short loc_14002270D
0x1400226ce  cmp     r8d, 1
0x1400226d2  jz      short loc_1400226DE
0x1400226d4  add     r10, 0FFFFFFFFFFFFFFFEh
0x1400226d8  add     rdx, 2
0x1400226dc  jmp     short loc_140022754
0x1400226de  movzx   eax, byte ptr [rsi+5]
0x1400226e2  lea     r9, [rbp+pcbRemaining]; pcbRemaining
0x1400226e6  mov     dword ptr [rsp+60h+var_30], eax
0x1400226ea  lea     r8, [rbp+ppszDestEnd]; ppszDestEnd
0x1400226ee  lea     rax, aUsbClass02xSub_2; "USB\\Class_%02x&SubClass_Modem"
0x1400226f5  mov     rcx, r10; pszDest
0x1400226f8  mov     [rsp+60h+pszFormat], rax; pszFormat
0x1400226fd  mov     qword ptr [rsp+60h+dwFlags], 0; dwFlags
0x140022706  call    RtlStringCbPrintfExW
0x14002270b  jmp     short loc_140022742
0x14002270d  movzx   eax, byte ptr [rsi+6]
0x140022711  lea     r9, [rbp+pcbRemaining]; pcbRemaining
0x140022715  movzx   ecx, byte ptr [rsi+5]
0x140022719  lea     r8, [rbp+ppszDestEnd]; ppszDestEnd
0x14002271d  mov     dword ptr [rsp+60h+var_28], eax
0x140022721  lea     rax, aUsbClass02xSub; "USB\\Class_%02x&SubClass_%02x"
0x140022728  mov     dword ptr [rsp+60h+var_30], ecx
0x14002272c  mov     rcx, r10; pszDest
0x14002272f  mov     [rsp+60h+pszFormat], rax; pszFormat
0x140022734  mov     qword ptr [rsp+60h+dwFlags], 0; dwFlags
0x14002273d  call    RtlStringCbPrintfExW
0x140022742  mov     ecx, eax
0x140022744  test    eax, eax
0x140022746  js      loc_1400227F1
0x14002274c  mov     r10, [rbp+ppszDestEnd]
0x140022750  mov     rdx, [rbp+pcbRemaining]
0x140022754  cmp     rdx, 2
0x140022758  jbe     loc_1400227E5
0x14002275e  xor     eax, eax
0x140022760  sub     rdx, 2; cbDest
0x140022764  mov     [r10], ax
0x140022768  add     r10, 2
0x14002276c  mov     [rbp+ppszDestEnd], r10
0x140022770  mov     [rbp+pcbRemaining], rdx
0x140022774  sub     ebx, 1
0x140022777  jz      short loc_140022792
0x140022779  sub     ebx, 1
0x14002277c  jz      short loc_140022792
0x14002277e  sub     ebx, 1
0x140022781  jz      short loc_140022792
0x140022783  cmp     ebx, 1
0x140022786  jz      short loc_140022792
0x140022788  add     r10, 0FFFFFFFFFFFFFFFEh
0x14002278c  add     rdx, 2
0x140022790  jmp     short loc_1400227CD
0x140022792  movzx   eax, byte ptr [rsi+5]
0x140022796  lea     r9, [rbp+pcbRemaining]; pcbRemaining
0x14002279a  mov     dword ptr [rsp+60h+var_30], eax
0x14002279e  lea     r8, [rbp+ppszDestEnd]; ppszDestEnd
0x1400227a2  lea     rax, aUsbClass02x; "USB\\Class_%02x"
0x1400227a9  mov     rcx, r10; pszDest
0x1400227ac  mov     [rsp+60h+pszFormat], rax; pszFormat
0x1400227b1  mov     qword ptr [rsp+60h+dwFlags], 0; dwFlags
0x1400227ba  call    RtlStringCbPrintfExW
0x1400227bf  mov     ecx, eax
0x1400227c1  test    eax, eax
0x1400227c3  js      short loc_1400227F1
0x1400227c5  mov     r10, [rbp+ppszDestEnd]
0x1400227c9  mov     rdx, [rbp+pcbRemaining]
0x1400227cd  cmp     rdx, 4
0x1400227d1  jbe     short loc_1400227E5
0x1400227d3  xor     eax, eax
0x1400227d5  sub     rdx, 4
0x1400227d9  sub     di, dx
0x1400227dc  mov     [r10], eax
0x1400227df  mov     [r14], di
0x1400227e3  jmp     short loc_1400227F1
0x1400227e5  mov     ecx, 80000005h
0x1400227ea  jmp     short loc_1400227F1
0x1400227ec  mov     ecx, 0C00000E5h
0x1400227f1  lea     r11, [rsp+60h+var_s0]
0x1400227f6  mov     eax, ecx
0x1400227f8  mov     rbx, [r11+28h]
0x1400227fc  mov     rsi, [r11+30h]
0x140022800  mov     rsp, r11
0x140022803  pop     r14
0x140022805  pop     rdi
0x140022806  pop     rbp
0x140022807  retn
```
