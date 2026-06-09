# LOG_SVC_ADMIN::SetConfigChangeHandler(int)

- ea: `0x18000cdbc`
- end: `0x18000cf0e`
- name: `?SetConfigChangeHandler@LOG_SVC_ADMIN@@AEAAJH@Z`
- size: `338`
- prototype: `__int64 __fastcall(LOG_SVC_ADMIN *__hidden this, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000bfc0`
- `0x18000d180`

## callees

- `0x180001008`
- `0x18000cdbc`
- `0x180010010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000cdf4`
- `OLEAUT32!__imp_SysAllocString` at `0x18000cdf4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ced2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ced2`
- `OLEAUT32!__imp_VariantInit` at `0x18000cde7`
- `OLEAUT32!__imp_VariantInit` at `0x18000cde7`
- `OLEAUT32!__imp_VariantClear` at `0x18000cec4`
- `OLEAUT32!__imp_VariantClear` at `0x18000cec4`

## pseudocode

```c
__int64 __fastcall LOG_SVC_ADMIN::SetConfigChangeHandler(LOG_SVC_ADMIN *this, int a2)
{
  OLECHAR *v4; // r14
  int v5; // edi
  LONGLONG *v6; // rbx
  __int64 v7; // rcx
  _DWORD *v8; // rcx
  __int64 *v9; // rcx
  __int64 v10; // rax
  VARIANTARG pvarg; // [rsp+20h] [rbp-40h] BYREF
  VARIANTARG v13; // [rsp+40h] [rbp-20h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v4 = SysAllocString(L"changeHandler");
  if ( !v4 )
  {
    v5 = -2147024882;
    v6 = (LONGLONG *)((char *)this + 32);
    goto LABEL_14;
  }
  if ( a2 )
  {
    v6 = (LONGLONG *)((char *)this + 32);
    v7 = *((_QWORD *)this + 4);
    if ( v7 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      *v6 = 0;
    }
    pvarg.vt = 0;
  }
  else
  {
    v8 = operator new(0x10u);
    if ( v8 )
    {
      v8[2] = 1;
      *(_QWORD *)v8 = &LOG_SVC_CONFIG_CHANGE_HANDLER::`vftable';
    }
    else
    {
      v8 = 0;
    }
    v6 = (LONGLONG *)((char *)this + 32);
    *((_QWORD *)this + 4) = v8;
    if ( !v8 )
    {
      v5 = -2147024882;
      goto LABEL_14;
    }
    pvarg.vt = 13;
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 8LL))(v8);
    pvarg.llVal = *v6;
  }
  v9 = (__int64 *)*((_QWORD *)this + 2);
  v10 = *v9;
  v13 = pvarg;
  v5 = (*(__int64 (__fastcall **)(__int64 *, OLECHAR *, VARIANTARG *))(v10 + 40))(v9, v4, &v13);
LABEL_14:
  VariantClear(&pvarg);
  if ( v4 )
    SysFreeString(v4);
  if ( v5 < 0 && *v6 )
  {
    (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)*v6 + 16LL))(*v6);
    *v6 = 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000cdbc  mov     [rsp-18h+arg_0], rbx
0x18000cdc1  mov     [rsp-18h+arg_8], rsi
0x18000cdc6  push    rbp
0x18000cdc7  push    rdi
0x18000cdc8  push    r14
0x18000cdca  mov     rbp, rsp
0x18000cdcd  sub     rsp, 60h
0x18000cdd1  mov     rsi, rcx
0x18000cdd4  xorps   xmm0, xmm0
0x18000cdd7  xor     eax, eax
0x18000cdd9  lea     rcx, [rbp+pvarg]; pvarg
0x18000cddd  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000cde1  mov     qword ptr [rbp+pvarg+10h], rax
0x18000cde5  mov     ebx, edx
0x18000cde7  call    cs:__imp_VariantInit
0x18000cded  lea     rcx, aChangehandler; "changeHandler"
0x18000cdf4  call    cs:__imp_SysAllocString
0x18000cdfa  mov     r14, rax
0x18000cdfd  test    rax, rax
0x18000ce00  jnz     short loc_18000CE10
0x18000ce02  mov     edi, 8007000Eh
0x18000ce07  lea     rbx, [rsi+20h]
0x18000ce0b  jmp     loc_18000CEC0
0x18000ce10  test    ebx, ebx
0x18000ce12  jz      short loc_18000CE3B
0x18000ce14  lea     rbx, [rsi+20h]
0x18000ce18  mov     rcx, [rbx]
0x18000ce1b  test    rcx, rcx
0x18000ce1e  jz      short loc_18000CE33
0x18000ce20  mov     rax, [rcx]
0x18000ce23  mov     rax, [rax+10h]
0x18000ce27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce2c  mov     qword ptr [rbx], 0
0x18000ce33  xor     eax, eax
0x18000ce35  mov     word ptr [rbp+pvarg], ax
0x18000ce39  jmp     short loc_18000CE95
0x18000ce3b  mov     ecx, 10h; Size
0x18000ce40  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ce45  mov     [rbp+arg_10], rax
0x18000ce49  mov     rcx, rax
0x18000ce4c  test    rax, rax
0x18000ce4f  jz      short loc_18000CE64
0x18000ce51  lea     rax, ??_7LOG_SVC_CONFIG_CHANGE_HANDLER@@6B@; const LOG_SVC_CONFIG_CHANGE_HANDLER::`vftable'
0x18000ce58  mov     dword ptr [rcx+8], 1
0x18000ce5f  mov     [rcx], rax
0x18000ce62  jmp     short loc_18000CE66
0x18000ce64  xor     ecx, ecx
0x18000ce66  lea     rbx, [rsi+20h]
0x18000ce6a  mov     [rbx], rcx
0x18000ce6d  test    rcx, rcx
0x18000ce70  jnz     short loc_18000CE79
0x18000ce72  mov     edi, 8007000Eh
0x18000ce77  jmp     short loc_18000CEC0
0x18000ce79  mov     eax, 0Dh
0x18000ce7e  mov     word ptr [rbp+pvarg], ax
0x18000ce82  mov     rax, [rcx]
0x18000ce85  mov     rax, [rax+8]
0x18000ce89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce8e  mov     rax, [rbx]
0x18000ce91  mov     qword ptr [rbp+pvarg+8], rax
0x18000ce95  mov     rcx, [rsi+10h]
0x18000ce99  lea     r8, [rbp+var_20]
0x18000ce9d  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18000cea1  mov     rdx, r14
0x18000cea4  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18000cea9  mov     rax, [rcx]
0x18000ceac  movaps  [rbp+var_20], xmm0
0x18000ceb0  movsd   [rbp+var_10], xmm1
0x18000ceb5  mov     rax, [rax+28h]
0x18000ceb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cebe  mov     edi, eax
0x18000cec0  lea     rcx, [rbp+pvarg]; pvarg
0x18000cec4  call    cs:__imp_VariantClear
0x18000ceca  test    r14, r14
0x18000cecd  jz      short loc_18000CED8
0x18000cecf  mov     rcx, r14; bstrString
0x18000ced2  call    cs:__imp_SysFreeString
0x18000ced8  test    edi, edi
0x18000ceda  jns     short loc_18000CEF7
0x18000cedc  mov     rcx, [rbx]
0x18000cedf  test    rcx, rcx
0x18000cee2  jz      short loc_18000CEF7
0x18000cee4  mov     rax, [rcx]
0x18000cee7  mov     rax, [rax+10h]
0x18000ceeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cef0  mov     qword ptr [rbx], 0
0x18000cef7  lea     r11, [rsp+60h+var_s0]
0x18000cefc  mov     eax, edi
0x18000cefe  mov     rbx, [r11+20h]
0x18000cf02  mov     rsi, [r11+28h]
0x18000cf06  mov     rsp, r11
0x18000cf09  pop     r14
0x18000cf0b  pop     rdi
0x18000cf0c  pop     rbp
0x18000cf0d  retn
```
