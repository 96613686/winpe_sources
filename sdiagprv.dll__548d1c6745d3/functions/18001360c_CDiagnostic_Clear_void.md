# CDiagnostic::Clear(void)

- ea: `0x18001360c`
- end: `0x180013745`
- name: `?Clear@CDiagnostic@@AEAAXXZ`
- size: `313`
- prototype: `void __fastcall(CDiagnostic *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800134ec`
- `0x18001374c`

## callees

- `0x18001360c`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001361e`
- `OLEAUT32!__imp_SysFreeString` at `0x180013635`
- `OLEAUT32!__imp_SysFreeString` at `0x18001364c`
- `OLEAUT32!__imp_SysFreeString` at `0x180013663`
- `OLEAUT32!__imp_SysFreeString` at `0x18001367a`
- `OLEAUT32!__imp_SysFreeString` at `0x180013691`
- `OLEAUT32!__imp_SysFreeString` at `0x1800136c8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800136e5`
- `OLEAUT32!__imp_SysFreeString` at `0x180013702`
- `OLEAUT32!__imp_SysFreeString` at `0x18001361e`
- `OLEAUT32!__imp_SysFreeString` at `0x180013635`
- `OLEAUT32!__imp_SysFreeString` at `0x18001364c`
- `OLEAUT32!__imp_SysFreeString` at `0x180013663`
- `OLEAUT32!__imp_SysFreeString` at `0x18001367a`
- `OLEAUT32!__imp_SysFreeString` at `0x180013691`
- `OLEAUT32!__imp_SysFreeString` at `0x1800136c8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800136e5`
- `OLEAUT32!__imp_SysFreeString` at `0x180013702`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800136ab`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001371f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800136ab`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001371f`

## pseudocode

```c
void __fastcall CDiagnostic::Clear(CDiagnostic *this)
{
  OLECHAR *v2; // rcx
  OLECHAR *v3; // rcx
  OLECHAR *v4; // rcx
  OLECHAR *v5; // rcx
  OLECHAR *v6; // rcx
  OLECHAR *v7; // rcx
  SAFEARRAY *v8; // rcx
  OLECHAR *v9; // rcx
  OLECHAR *v10; // rcx
  OLECHAR *v11; // rcx
  SAFEARRAY *v12; // rcx

  v2 = (OLECHAR *)*((_QWORD *)this + 9);
  if ( v2 )
  {
    SysFreeString(v2);
    *((_QWORD *)this + 9) = 0;
  }
  v3 = (OLECHAR *)*((_QWORD *)this + 10);
  if ( v3 )
  {
    SysFreeString(v3);
    *((_QWORD *)this + 10) = 0;
  }
  v4 = (OLECHAR *)*((_QWORD *)this + 11);
  if ( v4 )
  {
    SysFreeString(v4);
    *((_QWORD *)this + 11) = 0;
  }
  v5 = (OLECHAR *)*((_QWORD *)this + 12);
  if ( v5 )
  {
    SysFreeString(v5);
    *((_QWORD *)this + 12) = 0;
  }
  v6 = (OLECHAR *)*((_QWORD *)this + 14);
  if ( v6 )
  {
    SysFreeString(v6);
    *((_QWORD *)this + 14) = 0;
  }
  v7 = (OLECHAR *)*((_QWORD *)this + 15);
  if ( v7 )
  {
    SysFreeString(v7);
    *((_QWORD *)this + 15) = 0;
  }
  v8 = (SAFEARRAY *)*((_QWORD *)this + 16);
  if ( v8 )
  {
    SafeArrayDestroy(v8);
    *((_QWORD *)this + 16) = 0;
  }
  v9 = (OLECHAR *)*((_QWORD *)this + 17);
  if ( v9 )
  {
    SysFreeString(v9);
    *((_QWORD *)this + 17) = 0;
  }
  v10 = (OLECHAR *)*((_QWORD *)this + 18);
  if ( v10 )
  {
    SysFreeString(v10);
    *((_QWORD *)this + 18) = 0;
  }
  v11 = (OLECHAR *)*((_QWORD *)this + 19);
  if ( v11 )
  {
    SysFreeString(v11);
    *((_QWORD *)this + 19) = 0;
  }
  v12 = (SAFEARRAY *)*((_QWORD *)this + 20);
  if ( v12 )
  {
    SafeArrayDestroy(v12);
    *((_QWORD *)this + 20) = 0;
  }
  *((_WORD *)this + 84) = -1;
  *((_WORD *)this + 52) = 0;
}

```

## disassembly

```asm
0x18001360c  push    rbx
0x18001360e  sub     rsp, 20h
0x180013612  mov     rbx, rcx
0x180013615  mov     rcx, [rcx+48h]; bstrString
0x180013619  test    rcx, rcx
0x18001361c  jz      short loc_18001362C
0x18001361e  call    cs:__imp_SysFreeString
0x180013624  mov     qword ptr [rbx+48h], 0
0x18001362c  mov     rcx, [rbx+50h]; bstrString
0x180013630  test    rcx, rcx
0x180013633  jz      short loc_180013643
0x180013635  call    cs:__imp_SysFreeString
0x18001363b  mov     qword ptr [rbx+50h], 0
0x180013643  mov     rcx, [rbx+58h]; bstrString
0x180013647  test    rcx, rcx
0x18001364a  jz      short loc_18001365A
0x18001364c  call    cs:__imp_SysFreeString
0x180013652  mov     qword ptr [rbx+58h], 0
0x18001365a  mov     rcx, [rbx+60h]; bstrString
0x18001365e  test    rcx, rcx
0x180013661  jz      short loc_180013671
0x180013663  call    cs:__imp_SysFreeString
0x180013669  mov     qword ptr [rbx+60h], 0
0x180013671  mov     rcx, [rbx+70h]; bstrString
0x180013675  test    rcx, rcx
0x180013678  jz      short loc_180013688
0x18001367a  call    cs:__imp_SysFreeString
0x180013680  mov     qword ptr [rbx+70h], 0
0x180013688  mov     rcx, [rbx+78h]; bstrString
0x18001368c  test    rcx, rcx
0x18001368f  jz      short loc_18001369F
0x180013691  call    cs:__imp_SysFreeString
0x180013697  mov     qword ptr [rbx+78h], 0
0x18001369f  mov     rcx, [rbx+80h]; psa
0x1800136a6  test    rcx, rcx
0x1800136a9  jz      short loc_1800136BC
0x1800136ab  call    cs:__imp_SafeArrayDestroy
0x1800136b1  mov     qword ptr [rbx+80h], 0
0x1800136bc  mov     rcx, [rbx+88h]; bstrString
0x1800136c3  test    rcx, rcx
0x1800136c6  jz      short loc_1800136D9
0x1800136c8  call    cs:__imp_SysFreeString
0x1800136ce  mov     qword ptr [rbx+88h], 0
0x1800136d9  mov     rcx, [rbx+90h]; bstrString
0x1800136e0  test    rcx, rcx
0x1800136e3  jz      short loc_1800136F6
0x1800136e5  call    cs:__imp_SysFreeString
0x1800136eb  mov     qword ptr [rbx+90h], 0
0x1800136f6  mov     rcx, [rbx+98h]; bstrString
0x1800136fd  test    rcx, rcx
0x180013700  jz      short loc_180013713
0x180013702  call    cs:__imp_SysFreeString
0x180013708  mov     qword ptr [rbx+98h], 0
0x180013713  mov     rcx, [rbx+0A0h]; psa
0x18001371a  test    rcx, rcx
0x18001371d  jz      short loc_180013730
0x18001371f  call    cs:__imp_SafeArrayDestroy
0x180013725  mov     qword ptr [rbx+0A0h], 0
0x180013730  xor     eax, eax
0x180013732  mov     word ptr [rbx+0A8h], 0FFFFh
0x18001373b  mov     [rbx+68h], ax
0x18001373f  add     rsp, 20h
0x180013743  pop     rbx
0x180013744  retn
```
