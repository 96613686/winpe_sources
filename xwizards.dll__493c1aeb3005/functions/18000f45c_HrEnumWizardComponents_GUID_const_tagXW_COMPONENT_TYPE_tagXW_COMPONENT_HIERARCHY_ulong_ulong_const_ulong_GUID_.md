# HrEnumWizardComponents(_GUID const *,tagXW_COMPONENT_TYPE,tagXW_COMPONENT_HIERARCHY,ulong,ulong * const,ulong,_GUID * *,ulong *)

- ea: `0x18000f45c`
- end: `0x18000f5c6`
- name: `?HrEnumWizardComponents@@YAJPEBU_GUID@@W4tagXW_COMPONENT_TYPE@@W4tagXW_COMPONENT_HIERARCHY@@KQEAKKPEAPEAU1@PEAK@Z`
- size: `362`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006a50`
- `0x180006a90`
- `0x180006ad0`

## callees

- `0x18000ae04`
- `0x18000edd8`
- `0x18000f45c`
- `0x180032a02`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f4f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f4f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f537`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f554`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f537`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f554`

## pseudocode

```c
__int64 __fastcall HrEnumWizardComponents(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5,
        unsigned int a6,
        void *a7,
        _DWORD *a8)
{
  int v9; // edi
  __int64 v10; // rsi
  LPVOID v11; // rax
  void *v12; // rbp
  int WizardComponent; // eax
  __int64 v14; // rbp

  if ( a7 && (a8 || a6 == 1) )
  {
    if ( a4 < 2 )
    {
      v9 = 0;
      v10 = 0;
      if ( a8 )
        *a8 = 0;
      memset_0(a7, 0, 8LL * a6);
      while ( (unsigned int)v10 < a6 )
      {
        v11 = CoTaskMemAlloc(0x10u);
        v12 = v11;
        if ( !v11 )
        {
          v9 = -2147024882;
          goto LABEL_18;
        }
        WizardComponent = HrNextWizardComponent(a1, a2, a3, a4, a5, v11);
        v9 = WizardComponent;
        if ( WizardComponent )
        {
          if ( WizardComponent == 1 )
          {
            CoTaskMemFree(v12);
            break;
          }
          if ( WizardComponent < 0 )
          {
LABEL_18:
            v14 = 0;
            if ( !(_DWORD)v10 )
              goto LABEL_24;
            do
            {
              CoTaskMemFree(*((LPVOID *)a7 + v14));
              *((_QWORD *)a7 + v14) = 0;
              v14 = (unsigned int)(v14 + 1);
            }
            while ( (unsigned int)v14 < (unsigned int)v10 );
          }
          if ( v9 < 0 )
            goto LABEL_24;
          break;
        }
        *((_QWORD *)a7 + v10) = v12;
        v10 = (unsigned int)(v10 + 1);
      }
      if ( a8 )
        *a8 = v10;
    }
    else
    {
      v9 = -2147024809;
    }
  }
  else
  {
    v9 = -2147467261;
  }
LABEL_24:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_f7b22b8d1fc83d52a54db5e3c505ff82_Traceguids, (unsigned int)v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000f45c  mov     rax, rsp
0x18000f45f  mov     [rax+20h], rbx
0x18000f463  mov     [rax+18h], r8d
0x18000f467  mov     [rax+10h], edx
0x18000f46a  mov     [rax+8], rcx
0x18000f46e  push    rbp
0x18000f46f  push    rsi
0x18000f470  push    rdi
0x18000f471  push    r12
0x18000f473  push    r13
0x18000f475  push    r14
0x18000f477  push    r15
0x18000f479  sub     rsp, 30h
0x18000f47d  mov     r15, [rsp+68h+arg_30]
0x18000f485  mov     r12d, r9d
0x18000f488  test    r15, r15
0x18000f48b  jz      loc_18000F576
0x18000f491  mov     r14, [rsp+68h+arg_38]
0x18000f499  mov     ebx, [rsp+68h+arg_28]
0x18000f4a0  test    r14, r14
0x18000f4a3  jnz     short loc_18000F4AE
0x18000f4a5  cmp     ebx, 1
0x18000f4a8  jnz     loc_18000F576
0x18000f4ae  cmp     r12d, 2
0x18000f4b2  jb      short loc_18000F4BE
0x18000f4b4  mov     edi, 80070057h
0x18000f4b9  jmp     loc_18000F57B
0x18000f4be  xor     edi, edi
0x18000f4c0  xor     esi, esi
0x18000f4c2  test    r14, r14
0x18000f4c5  jz      short loc_18000F4CA
0x18000f4c7  mov     [r14], esi
0x18000f4ca  mov     r8, rbx
0x18000f4cd  xor     edx, edx; Val
0x18000f4cf  shl     r8, 3; Size
0x18000f4d3  mov     rcx, r15; void *
0x18000f4d6  call    memset_0
0x18000f4db  mov     r13, [rsp+68h+arg_20]
0x18000f4e3  cmp     esi, ebx
0x18000f4e5  jnb     loc_18000F56C
0x18000f4eb  mov     ecx, 10h; cb
0x18000f4f0  call    cs:__imp_CoTaskMemAlloc
0x18000f4f6  mov     rbp, rax
0x18000f4f9  test    rax, rax
0x18000f4fc  jz      short loc_18000F545
0x18000f4fe  mov     r8d, [rsp+68h+arg_10]
0x18000f506  mov     r9d, r12d
0x18000f509  mov     edx, [rsp+68h+arg_8]
0x18000f50d  mov     rcx, [rsp+68h+arg_0]
0x18000f512  mov     [rsp+68h+var_40], rax
0x18000f517  mov     [rsp+68h+var_48], r13
0x18000f51c  call    ?HrNextWizardComponent@@YAJPEBU_GUID@@W4tagXW_COMPONENT_TYPE@@W4tagXW_COMPONENT_HIERARCHY@@KQEAKPEAU1@@Z; HrNextWizardComponent(_GUID const *,tagXW_COMPONENT_TYPE,tagXW_COMPONENT_HIERARCHY,ulong,ulong * const,_GUID *)
0x18000f521  mov     edi, eax
0x18000f523  test    eax, eax
0x18000f525  jnz     short loc_18000F52F
0x18000f527  mov     [r15+rsi*8], rbp
0x18000f52b  inc     esi
0x18000f52d  jmp     short loc_18000F4E3
0x18000f52f  cmp     eax, 1
0x18000f532  jnz     short loc_18000F53F
0x18000f534  mov     rcx, rbp; pv
0x18000f537  call    cs:__imp_CoTaskMemFree
0x18000f53d  jmp     short loc_18000F56C
0x18000f53f  test    eax, eax
0x18000f541  jns     short loc_18000F568
0x18000f543  jmp     short loc_18000F54A
0x18000f545  mov     edi, 8007000Eh
0x18000f54a  xor     ebp, ebp
0x18000f54c  test    esi, esi
0x18000f54e  jz      short loc_18000F57B
0x18000f550  mov     rcx, [r15+rbp*8]; pv
0x18000f554  call    cs:__imp_CoTaskMemFree
0x18000f55a  mov     qword ptr [r15+rbp*8], 0
0x18000f562  inc     ebp
0x18000f564  cmp     ebp, esi
0x18000f566  jb      short loc_18000F550
0x18000f568  test    edi, edi
0x18000f56a  js      short loc_18000F57B
0x18000f56c  test    r14, r14
0x18000f56f  jz      short loc_18000F57B
0x18000f571  mov     [r14], esi
0x18000f574  jmp     short loc_18000F57B
0x18000f576  mov     edi, 80004003h
0x18000f57b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f582  lea     rax, WPP_GLOBAL_Control
0x18000f589  cmp     rcx, rax
0x18000f58c  jz      short loc_18000F5AC
0x18000f58e  test    byte ptr [rcx+1Ch], 10h
0x18000f592  jz      short loc_18000F5AC
0x18000f594  mov     rcx, [rcx+10h]
0x18000f598  lea     r8, WPP_f7b22b8d1fc83d52a54db5e3c505ff82_Traceguids
0x18000f59f  mov     edx, 0Ah
0x18000f5a4  mov     r9d, edi
0x18000f5a7  call    WPP_SF_d
0x18000f5ac  mov     rbx, [rsp+68h+arg_18]
0x18000f5b4  mov     eax, edi
0x18000f5b6  add     rsp, 30h
0x18000f5ba  pop     r15
0x18000f5bc  pop     r14
0x18000f5be  pop     r13
0x18000f5c0  pop     r12
0x18000f5c2  pop     rdi
0x18000f5c3  pop     rsi
0x18000f5c4  pop     rbp
0x18000f5c5  retn
```
