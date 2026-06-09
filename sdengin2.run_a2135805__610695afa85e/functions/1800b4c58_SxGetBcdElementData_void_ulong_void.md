# SxGetBcdElementData(void *,ulong,void * *)

- ea: `0x1800b4c58`
- end: `0x1800b4e0e`
- name: `?SxGetBcdElementData@@YAJPEAXKPEAPEAX@Z`
- size: `438`
- prototype: `__int64 __fastcall(void *, unsigned int, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800b448c`

## callees

- `0x180008370`
- `0x180072e08`
- `0x180072f14`
- `0x180093698`
- `0x1800b4c58`
- `0x1800cf56a`

## import_xrefs

- `bcd!BcdGetElementData` at `0x1800b4d13`
- `bcd!BcdGetElementData` at `0x1800b4da1`
- `bcd!BcdGetElementData` at `0x1800b4d13`
- `bcd!BcdGetElementData` at `0x1800b4da1`
- `ole32!CoTaskMemFree` at `0x1800b4dde`
- `ole32!CoTaskMemFree` at `0x1800b4dde`
- `ole32!CoTaskMemAlloc` at `0x1800b4d5a`
- `ole32!CoTaskMemAlloc` at `0x1800b4d5a`

## pseudocode

```c
__int64 __fastcall SxGetBcdElementData(void *a1, unsigned int a2, void **a3, __int64 a4)
{
  void *v7; // rbx
  unsigned int ElementData; // eax
  __int16 v9; // ax
  unsigned int v10; // eax
  unsigned int v11; // ebx
  __int64 v13; // [rsp+20h] [rbp-40h] BYREF
  int v14; // [rsp+28h] [rbp-38h]
  SIZE_T cb; // [rsp+80h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b036215b3564316a9a5ab27768cd0679_Traceguids, a4);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v13, "SxGetBcdElementData", 0xFu, 1u);
  v7 = 0;
  LODWORD(cb) = 0;
  if ( a3 )
    *a3 = 0;
  if ( !a1 || a2 != 553648129 && a2 != 570425346 && a2 != 1174405136 || !a3 )
  {
    LODWORD(v13) = -2147024809;
    v9 = 27;
    goto LABEL_22;
  }
  LODWORD(v13) = 0;
  WORD2(v13) = 27;
  ElementData = BcdGetElementData(a1, a2, 0, &cb, v13);
  if ( ElementData != -1073741789 && ElementData != -2147483643 && ElementData != -1073741820 )
  {
    LODWORD(v13) = HRESULTFromNTSTATUS(ElementData);
    v9 = 34;
    if ( (int)v13 < 0 )
    {
      v14 = 1;
LABEL_22:
      HIWORD(v13) = v9;
      goto LABEL_23;
    }
    WORD2(v13) = 34;
  }
  v7 = CoTaskMemAlloc((unsigned int)cb);
  v9 = 38;
  if ( !v7 )
  {
    LODWORD(v13) = -2147024882;
    goto LABEL_22;
  }
  LODWORD(v13) = 0;
  WORD2(v13) = 38;
  memset_0(v7, 0, (unsigned int)cb);
  v10 = BcdGetElementData(a1, a2, v7, &cb, v13);
  LODWORD(v13) = HRESULTFromNTSTATUS(v10);
  v9 = 42;
  if ( (int)v13 < 0 )
    goto LABEL_22;
  *a3 = v7;
  v7 = 0;
  WORD2(v13) = 42;
LABEL_23:
  CoTaskMemFree(v7);
  v11 = v13;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v13);
  return v11;
}

```

## disassembly

```asm
0x1800b4c58  mov     [rsp-18h+arg_8], rbx
0x1800b4c5d  mov     [rsp-18h+arg_10], rsi
0x1800b4c62  push    rbp
0x1800b4c63  push    rdi
0x1800b4c64  push    r14
0x1800b4c66  mov     rbp, rsp
0x1800b4c69  sub     rsp, 60h
0x1800b4c6d  mov     rsi, r8
0x1800b4c70  mov     edi, edx
0x1800b4c72  mov     r14, rcx
0x1800b4c75  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4c7c  lea     rax, WPP_GLOBAL_Control
0x1800b4c83  cmp     rcx, rax
0x1800b4c86  jz      short loc_1800B4CA6
0x1800b4c88  test    dword ptr [rcx+1Ch], 20000000h
0x1800b4c8f  jz      short loc_1800B4CA6
0x1800b4c91  mov     rcx, [rcx+10h]
0x1800b4c95  lea     r8, WPP_b036215b3564316a9a5ab27768cd0679_Traceguids
0x1800b4c9c  mov     edx, 0Ah
0x1800b4ca1  call    WPP_SF_
0x1800b4ca6  mov     r9d, 1; unsigned __int16
0x1800b4cac  lea     rdx, aSxgetbcdelemen; "SxGetBcdElementData"
0x1800b4cb3  lea     rcx, [rbp+var_40]; this
0x1800b4cb7  lea     r8d, [r9+0Eh]; unsigned __int16
0x1800b4cbb  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800b4cc0  xor     ebx, ebx
0x1800b4cc2  mov     dword ptr [rbp+cb], ebx
0x1800b4cc5  test    rsi, rsi
0x1800b4cc8  jz      short loc_1800B4CCD
0x1800b4cca  mov     [rsi], rbx
0x1800b4ccd  test    r14, r14
0x1800b4cd0  jz      loc_1800B4DCB
0x1800b4cd6  cmp     edi, 21000001h
0x1800b4cdc  jz      short loc_1800B4CF2
0x1800b4cde  cmp     edi, 22000002h
0x1800b4ce4  jz      short loc_1800B4CF2
0x1800b4ce6  cmp     edi, 46000010h
0x1800b4cec  jnz     loc_1800B4DCB
0x1800b4cf2  test    rsi, rsi
0x1800b4cf5  jz      loc_1800B4DCB
0x1800b4cfb  mov     eax, 1Bh
0x1800b4d00  mov     [rbp+var_40], ebx
0x1800b4d03  lea     r9, [rbp+cb]
0x1800b4d07  mov     [rbp+var_3C], ax
0x1800b4d0b  xor     r8d, r8d
0x1800b4d0e  mov     edx, edi
0x1800b4d10  mov     rcx, r14
0x1800b4d13  call    cs:__imp_BcdGetElementData
0x1800b4d1a  nop     dword ptr [rax+rax+00h]
0x1800b4d1f  cmp     eax, 0C0000023h
0x1800b4d24  jz      short loc_1800B4D57
0x1800b4d26  cmp     eax, 80000005h
0x1800b4d2b  jz      short loc_1800B4D57
0x1800b4d2d  cmp     eax, 0C0000004h
0x1800b4d32  jz      short loc_1800B4D57
0x1800b4d34  mov     ecx, eax
0x1800b4d36  call    HRESULTFromNTSTATUS
0x1800b4d3b  mov     [rbp+var_40], eax
0x1800b4d3e  test    eax, eax
0x1800b4d40  mov     eax, 22h ; '"'
0x1800b4d45  jns     short loc_1800B4D53
0x1800b4d47  mov     [rbp+var_38], 1
0x1800b4d4e  jmp     loc_1800B4DD7
0x1800b4d53  mov     [rbp+var_3C], ax
0x1800b4d57  mov     ecx, dword ptr [rbp+cb]; cb
0x1800b4d5a  call    cs:__imp_CoTaskMemAlloc
0x1800b4d61  nop     dword ptr [rax+rax+00h]
0x1800b4d66  mov     rbx, rax
0x1800b4d69  test    rax, rax
0x1800b4d6c  mov     eax, 26h ; '&'
0x1800b4d71  jnz     short loc_1800B4D7C
0x1800b4d73  mov     [rbp+var_40], 8007000Eh
0x1800b4d7a  jmp     short loc_1800B4DD7
0x1800b4d7c  mov     r8d, dword ptr [rbp+cb]; Size
0x1800b4d80  xor     edx, edx; Val
0x1800b4d82  mov     rcx, rbx; void *
0x1800b4d85  mov     [rbp+var_40], 0
0x1800b4d8c  mov     [rbp+var_3C], ax
0x1800b4d90  call    memset_0
0x1800b4d95  lea     r9, [rbp+cb]
0x1800b4d99  mov     r8, rbx
0x1800b4d9c  mov     edx, edi
0x1800b4d9e  mov     rcx, r14
0x1800b4da1  call    cs:__imp_BcdGetElementData
0x1800b4da8  nop     dword ptr [rax+rax+00h]
0x1800b4dad  mov     ecx, eax
0x1800b4daf  call    HRESULTFromNTSTATUS
0x1800b4db4  mov     [rbp+var_40], eax
0x1800b4db7  test    eax, eax
0x1800b4db9  mov     eax, 2Ah ; '*'
0x1800b4dbe  js      short loc_1800B4DD7
0x1800b4dc0  mov     [rsi], rbx
0x1800b4dc3  xor     ebx, ebx
0x1800b4dc5  mov     [rbp+var_3C], ax
0x1800b4dc9  jmp     short loc_1800B4DDB
0x1800b4dcb  mov     [rbp+var_40], 80070057h
0x1800b4dd2  mov     eax, 1Bh
0x1800b4dd7  mov     [rbp+var_3A], ax
0x1800b4ddb  mov     rcx, rbx; pv
0x1800b4dde  call    cs:__imp_CoTaskMemFree
0x1800b4de5  nop     dword ptr [rax+rax+00h]
0x1800b4dea  mov     ebx, [rbp+var_40]
0x1800b4ded  lea     rcx, [rbp+var_40]; this
0x1800b4df1  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800b4df6  lea     r11, [rsp+60h+var_s0]
0x1800b4dfb  mov     eax, ebx
0x1800b4dfd  mov     rbx, [r11+28h]
0x1800b4e01  mov     rsi, [r11+30h]
0x1800b4e05  mov     rsp, r11
0x1800b4e08  pop     r14
0x1800b4e0a  pop     rdi
0x1800b4e0b  pop     rbp
0x1800b4e0c  retn
```
