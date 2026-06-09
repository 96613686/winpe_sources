# CSWbemObjectPath::CompareObjectPaths(IWbemClassObject *,CWbemPathCracker &)

- ea: `0x18002e210`
- end: `0x18002e2e7`
- name: `?CompareObjectPaths@CSWbemObjectPath@@SA_NPEAUIWbemClassObject@@AEAVCWbemPathCracker@@@Z`
- size: `215`
- prototype: `static bool(struct IWbemClassObject *, struct CWbemPathCracker *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002c860`
- `0x1800317c0`

## callees

- `0x180017ce0`
- `0x18002e210`
- `0x180032db4`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002e2b6`
- `OLEAUT32!__imp_SysFreeString` at `0x18002e2b6`
- `OLEAUT32!__imp_VariantClear` at `0x18002e2d1`
- `OLEAUT32!__imp_VariantClear` at `0x18002e2d1`

## string_xrefs

- `0x18002e260`: `__RELPATH`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall CSWbemObjectPath::CompareObjectPaths(struct IWbemClassObject *a1, struct CWbemPathCracker *a2)
{
  char v3; // si
  OLECHAR *v4; // rbx
  __int64 v5; // rax
  VARIANTARG pvarg; // [rsp+40h] [rbp-28h] BYREF
  OLECHAR *v8; // [rsp+A8h] [rbp+40h] BYREF

  v3 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  pvarg.vt = 0;
  v4 = 0;
  v8 = 0;
  if ( *((_DWORD *)a2 + 7) == 1
    && ((int (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a1->lpVtbl->Get)(
         a1,
         L"__RELPATH",
         0,
         &pvarg,
         0,
         0) >= 0
    && pvarg.vt == 8 )
  {
    if ( pvarg.llVal )
    {
      v5 = -1;
      do
        ++v5;
      while ( *(_WORD *)(pvarg.llVal + 2 * v5) );
      if ( v5 )
      {
        ATL::CComBSTR::operator=(&v8);
        v3 = CWbemPathCracker::operator==(a2);
        v4 = v8;
      }
    }
  }
  SysFreeString(v4);
  if ( pvarg.vt == 4095 )
    pvarg.vt = 8;
  VariantClear(&pvarg);
  return v3;
}

```

## disassembly

```asm
0x18002e210  push    rbp
0x18002e212  push    rbx
0x18002e213  push    rsi
0x18002e214  push    rdi
0x18002e215  push    r14
0x18002e217  push    r15
0x18002e219  mov     rbp, rsp
0x18002e21c  sub     rsp, 68h
0x18002e220  mov     rdi, rdx
0x18002e223  xor     r14d, r14d
0x18002e226  mov     sil, r14b
0x18002e229  xorps   xmm0, xmm0
0x18002e22c  xor     eax, eax
0x18002e22e  movups  xmmword ptr [rbp+pvarg], xmm0
0x18002e232  mov     qword ptr [rbp+pvarg+10h], rax
0x18002e236  mov     word ptr [rbp+pvarg], r14w
0x18002e23b  mov     ebx, r14d
0x18002e23e  mov     [rbp+arg_8], rbx
0x18002e242  lea     r15d, [r14+8]
0x18002e246  cmp     dword ptr [rdx+1Ch], 1
0x18002e24a  jnz     short loc_18002E2B3
0x18002e24c  mov     rax, [rcx]
0x18002e24f  mov     [rsp+68h+var_40], r14
0x18002e254  mov     [rsp+68h+var_48], r14
0x18002e259  lea     r9, [rbp+pvarg]
0x18002e25d  xor     r8d, r8d
0x18002e260  lea     rdx, aRelpath; "__RELPATH"
0x18002e267  mov     rax, [rax+20h]
0x18002e26b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e270  test    eax, eax
0x18002e272  js      short loc_18002E2B3
0x18002e274  cmp     r15w, word ptr [rbp+pvarg]
0x18002e279  jnz     short loc_18002E2B3
0x18002e27b  mov     rdx, qword ptr [rbp+pvarg+8]
0x18002e27f  test    rdx, rdx
0x18002e282  jz      short loc_18002E2B3
0x18002e284  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002e288  inc     rax
0x18002e28b  cmp     [rdx+rax*2], r14w
0x18002e290  jnz     short loc_18002E288
0x18002e292  test    rax, rax
0x18002e295  jz      short loc_18002E2B3
0x18002e297  lea     rcx, [rbp+arg_8]
0x18002e29b  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18002e2a0  lea     rdx, [rbp+arg_8]
0x18002e2a4  mov     rcx, rdi; this
0x18002e2a7  call    ??8CWbemPathCracker@@QEAA_NAEBVCComBSTR@ATL@@@Z; CWbemPathCracker::operator==(ATL::CComBSTR const &)
0x18002e2ac  mov     sil, al
0x18002e2af  mov     rbx, [rbp+arg_8]
0x18002e2b3  mov     rcx, rbx; bstrString
0x18002e2b6  call    cs:__imp_SysFreeString
0x18002e2bc  nop
0x18002e2bd  mov     eax, 0FFFh
0x18002e2c2  cmp     word ptr [rbp+pvarg], ax
0x18002e2c6  jnz     short loc_18002E2CD
0x18002e2c8  mov     word ptr [rbp+pvarg], r15w
0x18002e2cd  lea     rcx, [rbp+pvarg]; pvarg
0x18002e2d1  call    cs:__imp_VariantClear
0x18002e2d7  mov     al, sil
0x18002e2da  add     rsp, 68h
0x18002e2de  pop     r15
0x18002e2e0  pop     r14
0x18002e2e2  pop     rdi
0x18002e2e3  pop     rsi
0x18002e2e4  pop     rbx
0x18002e2e5  pop     rbp
0x18002e2e6  retn
```
