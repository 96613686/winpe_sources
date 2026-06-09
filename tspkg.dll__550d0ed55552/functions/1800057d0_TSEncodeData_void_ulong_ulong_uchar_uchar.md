# TSEncodeData(void *,ulong,ulong *,uchar * *,uchar)

- ea: `0x1800057d0`
- end: `0x18000599f`
- name: `?TSEncodeData@@YAJPEAXKPEAKPEAPEAEE@Z`
- size: `463`
- prototype: `__int64 __fastcall(void *, unsigned int, unsigned int *, unsigned __int8 **, char)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180019460`
- `0x18001a700`

## callees

- `0x1800057d0`
- `0x18000c1a4`
- `0x18001c63c`
- `0x18001d010`

## import_xrefs

- `MSASN1!ASN1_CloseEncoder` at `0x1800058b9`
- `MSASN1!ASN1_CloseEncoder` at `0x1800058b9`
- `MSASN1!ASN1_CreateEncoder` at `0x180005813`
- `MSASN1!ASN1_CreateEncoder` at `0x180005813`
- `MSASN1!ASN1_CreateModule` at `0x180005983`
- `MSASN1!ASN1_CreateModule` at `0x180005983`
- `MSASN1!ASN1_Encode` at `0x18000583b`
- `MSASN1!ASN1_Encode` at `0x18000583b`
- `MSASN1!ASN1_FreeEncoded` at `0x18000589c`
- `MSASN1!ASN1_FreeEncoded` at `0x18000589c`

## pseudocode

```c
__int64 __fastcall TSEncodeData(void *a1, unsigned int a2, unsigned int *a3, unsigned __int8 **a4, char a5)
{
  __int64 Module; // rax
  __int64 v10; // rax
  unsigned __int8 *v11; // rdi
  unsigned int v12; // ebx
  __int64 v13; // rcx
  size_t v15; // rsi
  unsigned __int8 *v16; // rax
  _QWORD v17[7]; // [rsp+50h] [rbp-38h] BYREF

  v17[0] = 0;
  if ( fTSSSPModuleStarted )
  {
    Module = TSSSP_Module;
  }
  else
  {
    fTSSSPModuleStarted = 1;
    Module = ASN1_CreateModule(
               0x10000,
               1024,
               4096,
               6,
               off_18001E1E0,
               off_18001E1B0,
               off_18001E180,
               qword_18001F2E8,
               1936946036);
    TSSSP_Module = Module;
  }
  if ( (unsigned int)ASN1_CreateEncoder(Module, v17, 0, 0, 0) )
  {
    v12 = -1073741823;
  }
  else
  {
    if ( (int)ASN1_Encode(v17[0], a1, a2, 16, 0, 0) >= 0 )
    {
      if ( a5 )
      {
        v15 = *(unsigned int *)(v17[0] + 28LL);
        if ( TSGlobalState != 1 )
        {
          v16 = (unsigned __int8 *)((__int64 (__fastcall *)(_QWORD))TSGlobalDllFunctions->AllocateHeap)((unsigned int)v15);
          v11 = v16;
          if ( v16 )
            memset_0(v16, 0, v15);
          goto LABEL_8;
        }
        v10 = ((__int64 (__fastcall *)(_QWORD))TSGlobalLsaFunctions->AllocatePrivateHeap)((unsigned int)v15);
      }
      else
      {
        v10 = ((__int64 (__fastcall *)(_QWORD))TSGlobalLsaFunctions->AllocateLsaHeap)(*(unsigned int *)(v17[0] + 28LL));
      }
      v11 = (unsigned __int8 *)v10;
LABEL_8:
      *a4 = v11;
      if ( v11 )
      {
        v12 = 0;
        memcpy_0(v11, *(const void **)(v17[0] + 16LL), *(unsigned int *)(v17[0] + 28LL));
        v13 = v17[0];
        *a3 = *(_DWORD *)(v17[0] + 28LL);
      }
      else
      {
        v13 = v17[0];
        v12 = -1073741823;
      }
      ASN1_FreeEncoded(v13, *(_QWORD *)(v13 + 16));
      goto LABEL_11;
    }
    v12 = -1073741823;
  }
LABEL_11:
  if ( v17[0] )
    ASN1_CloseEncoder();
  return v12;
}

```

## disassembly

```asm
0x1800057d0  push    rbx
0x1800057d2  push    rbp
0x1800057d3  push    rsi
0x1800057d4  push    rdi
0x1800057d5  push    r14
0x1800057d7  sub     rsp, 60h
0x1800057db  xor     ebp, ebp
0x1800057dd  mov     rbx, r9
0x1800057e0  cmp     cs:?fTSSSPModuleStarted@@3HA, ebp; int fTSSSPModuleStarted
0x1800057e6  mov     r14, r8
0x1800057e9  mov     edi, edx
0x1800057eb  mov     [rsp+88h+var_38], rbp
0x1800057f0  mov     rsi, rcx
0x1800057f3  jz      loc_18000592B
0x1800057f9  mov     rax, cs:TSSSP_Module
0x180005800  xor     r9d, r9d
0x180005803  mov     [rsp+88h+var_68], rbp
0x180005808  xor     r8d, r8d
0x18000580b  lea     rdx, [rsp+88h+var_38]
0x180005810  mov     rcx, rax
0x180005813  call    cs:__imp_ASN1_CreateEncoder
0x180005819  test    eax, eax
0x18000581b  jnz     loc_180005995
0x180005821  mov     rcx, [rsp+88h+var_38]
0x180005826  mov     r9d, 10h
0x18000582c  mov     dword ptr [rsp+88h+var_60], ebp
0x180005830  mov     r8d, edi
0x180005833  mov     rdx, rsi
0x180005836  mov     [rsp+88h+var_68], rbp
0x18000583b  call    cs:__imp_ASN1_Encode
0x180005841  test    eax, eax
0x180005843  js      loc_1800058E9
0x180005849  cmp     [rsp+88h+arg_20], bpl
0x180005851  jnz     short loc_1800058C1
0x180005853  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x18000585a  mov     rcx, [rsp+88h+var_38]
0x18000585f  mov     rax, [rax+28h]
0x180005863  mov     ecx, [rcx+1Ch]
0x180005866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000586b  mov     rdi, rax
0x18000586e  mov     [rbx], rdi
0x180005871  test    rdi, rdi
0x180005874  jz      short loc_1800058F0
0x180005876  mov     rdx, [rsp+88h+var_38]
0x18000587b  mov     rcx, rdi; void *
0x18000587e  mov     ebx, ebp
0x180005880  mov     r8d, [rdx+1Ch]; Size
0x180005884  mov     rdx, [rdx+10h]; Src
0x180005888  call    memcpy_0
0x18000588d  mov     rcx, [rsp+88h+var_38]
0x180005892  mov     edx, [rcx+1Ch]
0x180005895  mov     [r14], edx
0x180005898  mov     rdx, [rcx+10h]
0x18000589c  call    cs:__imp_ASN1_FreeEncoded
0x1800058a2  mov     rcx, [rsp+88h+var_38]
0x1800058a7  test    rcx, rcx
0x1800058aa  jnz     short loc_1800058B9
0x1800058ac  mov     eax, ebx
0x1800058ae  add     rsp, 60h
0x1800058b2  pop     r14
0x1800058b4  pop     rdi
0x1800058b5  pop     rsi
0x1800058b6  pop     rbp
0x1800058b7  pop     rbx
0x1800058b8  retn
0x1800058b9  call    cs:__imp_ASN1_CloseEncoder
0x1800058bf  jmp     short loc_1800058AC
0x1800058c1  cmp     cs:?TSGlobalState@@3W4_TS_STATE@@A, 1; _TS_STATE TSGlobalState
0x1800058c8  mov     rax, [rsp+88h+var_38]
0x1800058cd  mov     esi, [rax+1Ch]
0x1800058d0  jnz     short loc_1800058FC
0x1800058d2  mov     rax, cs:?TSGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * TSGlobalLsaFunctions
0x1800058d9  mov     ecx, esi
0x1800058db  mov     rax, [rax+180h]
0x1800058e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058e7  jmp     short loc_18000586B
0x1800058e9  mov     ebx, 0C0000001h
0x1800058ee  jmp     short loc_1800058A2
0x1800058f0  mov     rcx, [rsp+88h+var_38]
0x1800058f5  mov     ebx, 0C0000001h
0x1800058fa  jmp     short loc_180005898
0x1800058fc  mov     rax, cs:?TSGlobalDllFunctions@@3PEAU_SECPKG_DLL_FUNCTIONS@@EA; _SECPKG_DLL_FUNCTIONS * TSGlobalDllFunctions
0x180005903  mov     ecx, esi
0x180005905  mov     rax, [rax]
0x180005908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000590d  mov     rdi, rax
0x180005910  test    rax, rax
0x180005913  jz      loc_18000586E
0x180005919  mov     r8, rsi; Size
0x18000591c  xor     edx, edx; Val
0x18000591e  mov     rcx, rax; void *
0x180005921  call    memset_0
0x180005926  jmp     loc_18000586E
0x18000592b  mov     [rsp+88h+var_48], 73737374h
0x180005933  lea     rax, qword_18001F2E8
0x18000593a  mov     [rsp+88h+var_50], rax
0x18000593f  mov     edx, 400h
0x180005944  lea     rax, off_18001E180
0x18000594b  mov     cs:?fTSSSPModuleStarted@@3HA, 1; int fTSSSPModuleStarted
0x180005955  mov     [rsp+88h+var_58], rax
0x18000595a  mov     ecx, 10000h
0x18000595f  lea     rax, off_18001E1B0
0x180005966  mov     r9d, 6
0x18000596c  mov     [rsp+88h+var_60], rax
0x180005971  mov     r8d, 1000h
0x180005977  lea     rax, off_18001E1E0
0x18000597e  mov     [rsp+88h+var_68], rax
0x180005983  call    cs:__imp_ASN1_CreateModule
0x180005989  mov     cs:TSSSP_Module, rax
0x180005990  jmp     loc_180005800
0x180005995  mov     ebx, 0C0000001h
0x18000599a  jmp     loc_1800058A2
```
