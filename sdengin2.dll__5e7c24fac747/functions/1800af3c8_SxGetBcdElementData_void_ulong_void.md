# SxGetBcdElementData(void *,ulong,void * *)

- ea: `0x1800af3c8`
- end: `0x1800af562`
- name: `?SxGetBcdElementData@@YAJPEAXKPEAPEAX@Z`
- size: `410`
- prototype: `__int64 __fastcall(void *, unsigned int, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800aec54`

## callees

- `0x1800081d8`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f660`
- `0x1800af3c8`
- `0x1800c97da`

## import_xrefs

- `bcd!BcdGetElementData` at `0x1800af483`
- `bcd!BcdGetElementData` at `0x1800af502`
- `bcd!BcdGetElementData` at `0x1800af483`
- `bcd!BcdGetElementData` at `0x1800af502`
- `ole32!CoTaskMemFree` at `0x1800af539`
- `ole32!CoTaskMemFree` at `0x1800af539`
- `ole32!CoTaskMemAlloc` at `0x1800af4c1`
- `ole32!CoTaskMemAlloc` at `0x1800af4c1`

## pseudocode

```c
__int64 __fastcall SxGetBcdElementData(void *a1, unsigned int a2, void **a3)
{
  void *v6; // rbx
  unsigned int ElementData; // eax
  __int16 v8; // ax
  unsigned int v9; // eax
  unsigned int v10; // ebx
  __int64 v12; // [rsp+20h] [rbp-40h] BYREF
  int v13; // [rsp+28h] [rbp-38h]
  SIZE_T cb; // [rsp+80h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b036215b3564316a9a5ab27768cd0679_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v12, "SxGetBcdElementData", 15, 1);
  v6 = 0;
  LODWORD(cb) = 0;
  if ( a3 )
    *a3 = 0;
  if ( !a1 || a2 != 553648129 && a2 != 570425346 && a2 != 1174405136 || !a3 )
  {
    LODWORD(v12) = -2147024809;
    v8 = 27;
    goto LABEL_22;
  }
  LODWORD(v12) = 0;
  WORD2(v12) = 27;
  ElementData = BcdGetElementData(a1, a2, 0, &cb, v12);
  if ( ElementData != -1073741789 && ElementData != -2147483643 && ElementData != -1073741820 )
  {
    LODWORD(v12) = HRESULTFromNTSTATUS(ElementData);
    v8 = 34;
    if ( (int)v12 < 0 )
    {
      v13 = 1;
LABEL_22:
      HIWORD(v12) = v8;
      goto LABEL_23;
    }
    WORD2(v12) = 34;
  }
  v6 = CoTaskMemAlloc((unsigned int)cb);
  v8 = 38;
  if ( !v6 )
  {
    LODWORD(v12) = -2147024882;
    goto LABEL_22;
  }
  LODWORD(v12) = 0;
  WORD2(v12) = 38;
  memset_0(v6, 0, (unsigned int)cb);
  v9 = BcdGetElementData(a1, a2, v6, &cb, v12);
  LODWORD(v12) = HRESULTFromNTSTATUS(v9);
  v8 = 42;
  if ( (int)v12 < 0 )
    goto LABEL_22;
  *a3 = v6;
  v6 = 0;
  WORD2(v12) = 42;
LABEL_23:
  CoTaskMemFree(v6);
  v10 = v12;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v12);
  return v10;
}

```

## disassembly

```asm
0x1800af3c8  mov     [rsp-18h+arg_8], rbx
0x1800af3cd  mov     [rsp-18h+arg_10], rsi
0x1800af3d2  push    rbp
0x1800af3d3  push    rdi
0x1800af3d4  push    r14
0x1800af3d6  mov     rbp, rsp
0x1800af3d9  sub     rsp, 60h
0x1800af3dd  mov     rsi, r8
0x1800af3e0  mov     edi, edx
0x1800af3e2  mov     r14, rcx
0x1800af3e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af3ec  lea     rax, WPP_GLOBAL_Control
0x1800af3f3  cmp     rcx, rax
0x1800af3f6  jz      short loc_1800AF416
0x1800af3f8  test    dword ptr [rcx+1Ch], 20000000h
0x1800af3ff  jz      short loc_1800AF416
0x1800af401  mov     rcx, [rcx+10h]
0x1800af405  lea     r8, WPP_b036215b3564316a9a5ab27768cd0679_Traceguids
0x1800af40c  mov     edx, 0Ah
0x1800af411  call    WPP_SF_
0x1800af416  mov     r9d, 1; unsigned __int16
0x1800af41c  lea     rdx, aSxgetbcdelemen; "SxGetBcdElementData"
0x1800af423  lea     rcx, [rbp+var_40]; this
0x1800af427  lea     r8d, [r9+0Eh]; unsigned __int16
0x1800af42b  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800af430  xor     ebx, ebx
0x1800af432  mov     dword ptr [rbp+cb], ebx
0x1800af435  test    rsi, rsi
0x1800af438  jz      short loc_1800AF43D
0x1800af43a  mov     [rsi], rbx
0x1800af43d  test    r14, r14
0x1800af440  jz      loc_1800AF526
0x1800af446  cmp     edi, 21000001h
0x1800af44c  jz      short loc_1800AF462
0x1800af44e  cmp     edi, 22000002h
0x1800af454  jz      short loc_1800AF462
0x1800af456  cmp     edi, 46000010h
0x1800af45c  jnz     loc_1800AF526
0x1800af462  test    rsi, rsi
0x1800af465  jz      loc_1800AF526
0x1800af46b  mov     eax, 1Bh
0x1800af470  mov     [rbp+var_40], ebx
0x1800af473  lea     r9, [rbp+cb]
0x1800af477  mov     [rbp+var_3C], ax
0x1800af47b  xor     r8d, r8d
0x1800af47e  mov     edx, edi
0x1800af480  mov     rcx, r14
0x1800af483  call    cs:__imp_BcdGetElementData
0x1800af489  cmp     eax, 0C0000023h
0x1800af48e  jz      short loc_1800AF4BE
0x1800af490  cmp     eax, 80000005h
0x1800af495  jz      short loc_1800AF4BE
0x1800af497  cmp     eax, 0C0000004h
0x1800af49c  jz      short loc_1800AF4BE
0x1800af49e  mov     ecx, eax
0x1800af4a0  call    HRESULTFromNTSTATUS
0x1800af4a5  mov     [rbp+var_40], eax
0x1800af4a8  test    eax, eax
0x1800af4aa  mov     eax, 22h ; '"'
0x1800af4af  jns     short loc_1800AF4BA
0x1800af4b1  mov     [rbp+var_38], 1
0x1800af4b8  jmp     short loc_1800AF532
0x1800af4ba  mov     [rbp+var_3C], ax
0x1800af4be  mov     ecx, dword ptr [rbp+cb]; cb
0x1800af4c1  call    cs:__imp_CoTaskMemAlloc
0x1800af4c7  mov     rbx, rax
0x1800af4ca  test    rax, rax
0x1800af4cd  mov     eax, 26h ; '&'
0x1800af4d2  jnz     short loc_1800AF4DD
0x1800af4d4  mov     [rbp+var_40], 8007000Eh
0x1800af4db  jmp     short loc_1800AF532
0x1800af4dd  mov     r8d, dword ptr [rbp+cb]; Size
0x1800af4e1  xor     edx, edx; Val
0x1800af4e3  mov     rcx, rbx; void *
0x1800af4e6  mov     [rbp+var_40], 0
0x1800af4ed  mov     [rbp+var_3C], ax
0x1800af4f1  call    memset_0
0x1800af4f6  lea     r9, [rbp+cb]
0x1800af4fa  mov     r8, rbx
0x1800af4fd  mov     edx, edi
0x1800af4ff  mov     rcx, r14
0x1800af502  call    cs:__imp_BcdGetElementData
0x1800af508  mov     ecx, eax
0x1800af50a  call    HRESULTFromNTSTATUS
0x1800af50f  mov     [rbp+var_40], eax
0x1800af512  test    eax, eax
0x1800af514  mov     eax, 2Ah ; '*'
0x1800af519  js      short loc_1800AF532
0x1800af51b  mov     [rsi], rbx
0x1800af51e  xor     ebx, ebx
0x1800af520  mov     [rbp+var_3C], ax
0x1800af524  jmp     short loc_1800AF536
0x1800af526  mov     [rbp+var_40], 80070057h
0x1800af52d  mov     eax, 1Bh
0x1800af532  mov     [rbp+var_3A], ax
0x1800af536  mov     rcx, rbx; pv
0x1800af539  call    cs:__imp_CoTaskMemFree
0x1800af53f  mov     ebx, [rbp+var_40]
0x1800af542  lea     rcx, [rbp+var_40]; this
0x1800af546  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800af54b  lea     r11, [rsp+60h+var_s0]
0x1800af550  mov     eax, ebx
0x1800af552  mov     rbx, [r11+28h]
0x1800af556  mov     rsi, [r11+30h]
0x1800af55a  mov     rsp, r11
0x1800af55d  pop     r14
0x1800af55f  pop     rdi
0x1800af560  pop     rbp
0x1800af561  retn
```
