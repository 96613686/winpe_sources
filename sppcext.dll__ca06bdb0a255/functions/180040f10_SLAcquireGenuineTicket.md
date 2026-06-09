# SLAcquireGenuineTicket

- ea: `0x180040f10`
- end: `0x180041125`
- name: `SLAcquireGenuineTicket`
- size: `533`
- prototype: `HRESULT __stdcall(void **ppTicketBlob, UINT *pcbTicketBlob, PCWSTR pwszTemplateId, PCWSTR pwszServerUrl, PCWSTR pwszClientToken)`
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x180004ca0`
- `0x180006c10`
- `0x18000760c`
- `0x180008954`
- `0x18003fa4c`
- `0x180040740`
- `0x180040f10`
- `0x180042514`
- `0x1800427f4`
- `0x180042acc`
- `0x180042db0`
- `0x180043088`
- `0x180043364`
- `0x18004362c`
- `0x180043900`
- `0x180043bd8`
- `0x180043eac`

## import_xrefs

- `sppc!SLOpen` at `0x180040fd0`
- `sppc!SLOpen` at `0x180040fd0`

## pseudocode

```c
HRESULT __stdcall SLAcquireGenuineTicket(
        void **ppTicketBlob,
        UINT *pcbTicketBlob,
        PCWSTR pwszTemplateId,
        PCWSTR pwszServerUrl,
        PCWSTR pwszClientToken)
{
  HRESULT v9; // edi
  __int64 v10; // rcx
  HRESULT v11; // eax
  int v13; // [rsp+50h] [rbp-20h] BYREF
  HSLC phSLC; // [rsp+58h] [rbp-18h] BYREF
  __int64 v15[2]; // [rsp+60h] [rbp-10h] BYREF

  phSLC = 0;
  v13 = 0;
  v15[0] = 0;
  if ( !pwszTemplateId )
    goto LABEL_2;
  sub_180042514(&dword_180085974, &dword_18008D114);
  if ( !pwszServerUrl )
  {
    sub_1800427F4(&dword_18008125C, byte_18008DBC0);
    goto LABEL_2;
  }
  if ( !ppTicketBlob )
  {
    v9 = -2147024809;
    sub_180042ACC(&dword_1800830C4, &dword_18008D9DC);
    goto LABEL_3;
  }
  sub_180043088(byte_180081A30, qword_18008E348);
  if ( !pcbTicketBlob )
  {
LABEL_2:
    v9 = -2147024809;
LABEL_3:
    v10 = 2147942487LL;
LABEL_16:
    sub_180004CA0(v10);
    goto LABEL_17;
  }
  v11 = SLOpen(&phSLC);
  v9 = v11;
  if ( v11 < 0 )
  {
    v10 = (unsigned int)v11;
    goto LABEL_16;
  }
  v9 = sub_18003FA4C(phSLC, (SLID *)&pQueryId, (__int64)v15);
  sub_180043364(byte_180082C00, &dword_18008CB4C);
  if ( (unsigned int)(v9 + 1073418220) <= 1 )
  {
    sub_180043900(qword_1800819C0, qword_18008E168);
    v9 = ((__int64 (__fastcall *)(int *, HSLC, PCWSTR, PCWSTR, PCWSTR, __int128 *, _QWORD, _DWORD, void **, UINT *))sub_180040740)(
           &v13,
           phSLC,
           pwszTemplateId,
           pwszServerUrl,
           pwszClientToken,
           &xmmword_180073828,
           0,
           0,
           ppTicketBlob,
           pcbTicketBlob);
    sub_180043BD8(&dword_1800852B4, qword_18008E090);
    if ( v9 >= 0 )
      goto LABEL_17;
LABEL_15:
    v10 = (unsigned int)v9;
    goto LABEL_16;
  }
  if ( v9 < 0 )
    goto LABEL_15;
  sub_180043EAC(byte_180082BF8, &dword_18008D62C);
  sub_180042DB0(&dword_180081CAC, &dword_18008E06C);
  v9 = -1073418218;
  sub_180004CA0(3221549078LL);
  sub_18004362C(qword_180083078, qword_18008D970);
LABEL_17:
  sub_180006C10((unsigned int)v9);
  sub_18000760C(v15);
  sub_180008954(&phSLC);
  return v9;
}

```

## disassembly

```asm
0x180040f10  mov     [rsp-28h+arg_0], rbx
0x180040f15  mov     [rsp-28h+arg_8], rsi
0x180040f1a  push    rbp
0x180040f1b  push    rdi
0x180040f1c  push    r12
0x180040f1e  push    r14
0x180040f20  push    r15
0x180040f22  mov     rbp, rsp
0x180040f25  sub     rsp, 70h
0x180040f29  mov     [rbp+phSLC], 0
0x180040f31  mov     r14, r9
0x180040f34  mov     [rbp+var_20], 0
0x180040f3b  mov     r12, r8
0x180040f3e  mov     [rbp+var_10], 0
0x180040f46  mov     r15, rdx
0x180040f49  mov     [rbp+arg_10], 0
0x180040f50  mov     rsi, rcx
0x180040f53  test    r8, r8
0x180040f56  jnz     short loc_180040F66
0x180040f58  mov     ebx, 80070057h
0x180040f5d  mov     edi, ebx
0x180040f5f  mov     ecx, ebx
0x180040f61  jmp     loc_1800410EC
0x180040f66  lea     rdx, dword_18008D114
0x180040f6d  lea     rcx, dword_180085974
0x180040f74  call    sub_180042514
0x180040f79  test    r14, r14
0x180040f7c  jnz     short loc_180040F93
0x180040f7e  lea     rdx, byte_18008DBC0
0x180040f85  lea     rcx, dword_18008125C
0x180040f8c  call    sub_1800427F4
0x180040f91  jmp     short loc_180040F58
0x180040f93  test    rsi, rsi
0x180040f96  jnz     short loc_180040FB4
0x180040f98  mov     ebx, 80070057h
0x180040f9d  lea     rdx, dword_18008D9DC
0x180040fa4  lea     rcx, dword_1800830C4
0x180040fab  mov     edi, ebx
0x180040fad  call    sub_180042ACC
0x180040fb2  jmp     short loc_180040F5F
0x180040fb4  lea     rdx, qword_18008E348
0x180040fbb  lea     rcx, byte_180081A30
0x180040fc2  call    sub_180043088
0x180040fc7  test    r15, r15
0x180040fca  jz      short loc_180040F58
0x180040fcc  lea     rcx, [rbp+phSLC]; phSLC
0x180040fd0  call    cs:SLOpen
0x180040fd6  mov     edi, eax
0x180040fd8  test    eax, eax
0x180040fda  jns     short loc_180040FE3
0x180040fdc  mov     ecx, eax
0x180040fde  jmp     loc_1800410EC
0x180040fe3  mov     rcx, [rbp+phSLC]; hSLC
0x180040fe7  lea     rax, [rbp+var_10]
0x180040feb  lea     r9, [rbp+arg_10]
0x180040fef  mov     [rsp+70h+var_50], rax; __int64
0x180040ff4  lea     rdx, pQueryId; pQueryId
0x180040ffb  call    sub_18003FA4C
0x180041000  lea     rdx, dword_18008CB4C
0x180041007  mov     edi, eax
0x180041009  lea     rcx, byte_180082C00
0x180041010  lea     ebx, [rax+3FFB0FECh]
0x180041016  call    sub_180043364
0x18004101b  cmp     ebx, 1
0x18004101e  jbe     short loc_18004107B
0x180041020  test    edi, edi
0x180041022  js      loc_1800410EA
0x180041028  lea     rdx, dword_18008D62C
0x18004102f  lea     rcx, byte_180082BF8
0x180041036  call    sub_180043EAC
0x18004103b  cmp     [rbp+arg_10], 1
0x18004103f  jz      short loc_180041075
0x180041041  lea     rdx, dword_18008E06C
0x180041048  lea     rcx, dword_180081CAC
0x18004104f  call    sub_180042DB0
0x180041054  mov     edi, 0C004F016h
0x180041059  mov     ecx, edi
0x18004105b  call    sub_180004CA0
0x180041060  lea     rdx, qword_18008D970
0x180041067  lea     rcx, qword_180083078
0x18004106e  call    sub_18004362C
0x180041073  jmp     short loc_1800410F1
0x180041075  mov     rbx, [rbp+var_10]
0x180041079  jmp     short loc_180041082
0x18004107b  lea     rbx, xmmword_180073828
0x180041082  lea     rdx, qword_18008E168
0x180041089  lea     rcx, qword_1800819C0
0x180041090  call    sub_180043900
0x180041095  mov     rax, [rbp+pwszClientToken]
0x180041099  lea     rcx, [rbp+var_20]
0x18004109d  mov     rdx, [rbp+phSLC]
0x1800410a1  mov     r9, r14
0x1800410a4  mov     [rsp+70h+var_28], r15
0x1800410a9  mov     r8, r12
0x1800410ac  mov     [rsp+70h+var_30], rsi
0x1800410b1  mov     [rsp+70h+var_38], 0
0x1800410b9  mov     [rsp+70h+var_40], 0
0x1800410c2  mov     [rsp+70h+var_48], rbx
0x1800410c7  mov     [rsp+70h+var_50], rax
0x1800410cc  call    sub_180040740
0x1800410d1  lea     rdx, qword_18008E090
0x1800410d8  mov     edi, eax
0x1800410da  lea     rcx, dword_1800852B4
0x1800410e1  call    sub_180043BD8
0x1800410e6  test    edi, edi
0x1800410e8  jns     short loc_1800410F1
0x1800410ea  mov     ecx, edi
0x1800410ec  call    sub_180004CA0
0x1800410f1  mov     ecx, edi
0x1800410f3  call    sub_180006C10
0x1800410f8  lea     rcx, [rbp+var_10]
0x1800410fc  call    sub_18000760C
0x180041101  lea     rcx, [rbp+phSLC]
0x180041105  call    sub_180008954
0x18004110a  lea     r11, [rsp+70h+var_s0]
0x18004110f  mov     eax, edi
0x180041111  mov     rbx, [r11+30h]
0x180041115  mov     rsi, [r11+38h]
0x180041119  mov     rsp, r11
0x18004111c  pop     r15
0x18004111e  pop     r14
0x180041120  pop     r12
0x180041122  pop     rdi
0x180041123  pop     rbp
0x180041124  retn
```
