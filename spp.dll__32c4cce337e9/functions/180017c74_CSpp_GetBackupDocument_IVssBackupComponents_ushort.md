# CSpp::_GetBackupDocument(IVssBackupComponents *,ushort * *)

- ea: `0x180017c74`
- end: `0x180017df3`
- name: `?_GetBackupDocument@CSpp@@AEAAJPEAVIVssBackupComponents@@PEAPEAG@Z`
- size: `383`
- prototype: `__int64 __fastcall(CSpp *__hidden this, struct IVssBackupComponents *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800090c0`
- `0x18001431c`

## callees

- `0x18000cbc0`
- `0x180017c74`
- `0x180020710`
- `0x1800268b4`
- `0x1800269ac`
- `0x180035b82`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017dcc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017dcc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017d8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017d8e`
- `OLEAUT32!__imp_SysFreeString` at `0x180017d20`
- `OLEAUT32!__imp_SysFreeString` at `0x180017dd9`
- `OLEAUT32!__imp_SysFreeString` at `0x180017d20`
- `OLEAUT32!__imp_SysFreeString` at `0x180017dd9`

## pseudocode

```c
__int64 __fastcall CSpp::_GetBackupDocument(CSpp *this, struct IVssBackupComponents *a2, unsigned __int16 **a3)
{
  __int16 v5; // ax
  __int64 v6; // rax
  bool v7; // zf
  SIZE_T v8; // rsi
  void *v9; // rdi
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // r8
  int v14; // [rsp+20h] [rbp-48h] BYREF
  __int16 v15; // [rsp+24h] [rbp-44h]
  __int16 v16; // [rsp+26h] [rbp-42h]
  void *Src; // [rsp+90h] [rbp+28h] BYREF

  Src = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v14, "CSpp::_GetBackupDocument", 4616, 1);
  Src = 0;
  if ( a3 )
    *a3 = 0;
  v5 = 4624;
  if ( a2 && (v15 = 4624, v5 = 4625, a3) )
  {
    v14 = 0;
    v15 = 4625;
    SysFreeString(0);
    v6 = *(_QWORD *)a2;
    Src = 0;
    v14 = (*(__int64 (__fastcall **)(struct IVssBackupComponents *, void **))(v6 + 208))(a2, &Src);
    v5 = 4634;
    if ( v14 >= 0 )
    {
      v15 = 4634;
      v7 = ATL::CComBSTR::Length((ATL::CComBSTR *)&Src) == 0;
      v5 = 4635;
      if ( v7 )
      {
        v14 = -2147418113;
      }
      else
      {
        v14 = 0;
        v15 = 4635;
        v8 = 2 * ATL::CComBSTR::Length((ATL::CComBSTR *)&Src) + 2;
        v9 = CoTaskMemAlloc(v8);
        v5 = 4638;
        if ( v9 )
        {
          v14 = 0;
          v15 = 4638;
          memcpy_0(v9, Src, v8);
          *a3 = (unsigned __int16 *)v9;
          goto LABEL_16;
        }
        v14 = -2147024882;
      }
    }
  }
  else
  {
    v14 = -2147024809;
  }
  v16 = v5;
LABEL_16:
  CoTaskMemFree(0);
  v10 = v14;
  SysFreeString((BSTR)Src);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v14, v11, v12);
  return v10;
}

```

## disassembly

```asm
0x180017c74  mov     [rsp-20h+Src], rcx
0x180017c79  push    rbp
0x180017c7a  push    rbx
0x180017c7b  push    rsi
0x180017c7c  push    rdi
0x180017c7d  mov     rbp, rsp
0x180017c80  sub     rsp, 68h
0x180017c84  mov     rbx, r8
0x180017c87  mov     rdi, rdx
0x180017c8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180017c91  lea     rax, WPP_GLOBAL_Control
0x180017c98  cmp     rcx, rax
0x180017c9b  jz      short loc_180017CBB
0x180017c9d  test    dword ptr [rcx+1Ch], 20000000h
0x180017ca4  jz      short loc_180017CBB
0x180017ca6  mov     rcx, [rcx+10h]
0x180017caa  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x180017cb1  mov     edx, 3Fh ; '?'
0x180017cb6  call    WPP_SF_
0x180017cbb  mov     r9d, 1; unsigned __int16
0x180017cc1  lea     rdx, aCsppGetbackupd; "CSpp::_GetBackupDocument"
0x180017cc8  mov     r8d, 1208h; unsigned __int16
0x180017cce  lea     rcx, [rbp+var_48]; this
0x180017cd2  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180017cd7  mov     [rbp+Src], 0
0x180017cdf  test    rbx, rbx
0x180017ce2  jz      short loc_180017CEB
0x180017ce4  mov     qword ptr [rbx], 0
0x180017ceb  mov     eax, 1210h
0x180017cf0  test    rdi, rdi
0x180017cf3  jnz     short loc_180017D05
0x180017cf5  mov     [rbp+var_48], 80070057h
0x180017cfc  mov     [rbp+var_42], ax
0x180017d00  jmp     loc_180017DCA
0x180017d05  mov     [rbp+var_44], ax
0x180017d09  mov     eax, 1211h
0x180017d0e  test    rbx, rbx
0x180017d11  jz      short loc_180017CF5
0x180017d13  xor     ecx, ecx; bstrString
0x180017d15  mov     [rbp+var_48], 0
0x180017d1c  mov     [rbp+var_44], ax
0x180017d20  call    cs:__imp_SysFreeString
0x180017d26  mov     rax, [rdi]
0x180017d29  lea     rdx, [rbp+Src]
0x180017d2d  mov     rcx, rdi
0x180017d30  mov     [rbp+Src], 0
0x180017d38  mov     rax, [rax+0D0h]
0x180017d3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d44  mov     [rbp+var_48], eax
0x180017d47  test    eax, eax
0x180017d49  mov     eax, 121Ah
0x180017d4e  js      short loc_180017CFC
0x180017d50  lea     rcx, [rbp+Src]; this
0x180017d54  mov     [rbp+var_44], ax
0x180017d58  call    ?Length@CComBSTR@ATL@@QEBAIXZ; ATL::CComBSTR::Length(void)
0x180017d5d  test    eax, eax
0x180017d5f  mov     eax, 121Bh
0x180017d64  jnz     short loc_180017D6F
0x180017d66  mov     [rbp+var_48], 8000FFFFh
0x180017d6d  jmp     short loc_180017CFC
0x180017d6f  lea     rcx, [rbp+Src]; this
0x180017d73  mov     [rbp+var_48], 0
0x180017d7a  mov     [rbp+var_44], ax
0x180017d7e  call    ?Length@CComBSTR@ATL@@QEBAIXZ; ATL::CComBSTR::Length(void)
0x180017d83  lea     eax, ds:2[rax*2]
0x180017d8a  mov     ecx, eax; cb
0x180017d8c  mov     esi, eax
0x180017d8e  call    cs:__imp_CoTaskMemAlloc
0x180017d94  mov     rdi, rax
0x180017d97  test    rax, rax
0x180017d9a  mov     eax, 121Eh
0x180017d9f  jnz     short loc_180017DAD
0x180017da1  mov     [rbp+var_48], 8007000Eh
0x180017da8  jmp     loc_180017CFC
0x180017dad  mov     rdx, [rbp+Src]; Src
0x180017db1  mov     r8, rsi; Size
0x180017db4  mov     rcx, rdi; void *
0x180017db7  mov     [rbp+var_48], 0
0x180017dbe  mov     [rbp+var_44], ax
0x180017dc2  call    memcpy_0
0x180017dc7  mov     [rbx], rdi
0x180017dca  xor     ecx, ecx; pv
0x180017dcc  call    cs:__imp_CoTaskMemFree
0x180017dd2  mov     rcx, [rbp+Src]; bstrString
0x180017dd6  mov     ebx, [rbp+var_48]
0x180017dd9  call    cs:__imp_SysFreeString
0x180017ddf  lea     rcx, [rbp+var_48]; this
0x180017de3  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180017de8  mov     eax, ebx
0x180017dea  add     rsp, 68h
0x180017dee  pop     rdi
0x180017def  pop     rsi
0x180017df0  pop     rbx
0x180017df1  pop     rbp
0x180017df2  retn
```
