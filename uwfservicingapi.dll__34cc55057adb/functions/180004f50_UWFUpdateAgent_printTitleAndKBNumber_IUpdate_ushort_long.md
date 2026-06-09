# UWFUpdateAgent::printTitleAndKBNumber(IUpdate *,ushort *,long)

- ea: `0x180004f50`
- end: `0x1800050e1`
- name: `?printTitleAndKBNumber@UWFUpdateAgent@@AEAAJPEAUIUpdate@@PEAGJ@Z`
- size: `401`
- prototype: `__int64 __fastcall(UWFUpdateAgent *this, struct IUpdate *, unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x1800045d0`
- `0x180004a70`

## callees

- `0x180004f50`
- `0x180006010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180004fc5`
- `msvcrt!wcscat_s` at `0x180005049`
- `msvcrt!wcscat_s` at `0x18000505c`
- `msvcrt!wcscat_s` at `0x180005097`
- `msvcrt!wcscat_s` at `0x1800050aa`
- `msvcrt!wcscat_s` at `0x180004fc5`
- `msvcrt!wcscat_s` at `0x180005049`
- `msvcrt!wcscat_s` at `0x18000505c`
- `msvcrt!wcscat_s` at `0x180005097`
- `msvcrt!wcscat_s` at `0x1800050aa`
- `msvcrt!swprintf_s` at `0x180004fb5`
- `msvcrt!swprintf_s` at `0x180004fb5`
- `OLEAUT32!__imp_SysFreeString` at `0x180004fcf`
- `OLEAUT32!__imp_SysFreeString` at `0x1800050b4`
- `OLEAUT32!__imp_SysFreeString` at `0x180004fcf`
- `OLEAUT32!__imp_SysFreeString` at `0x1800050b4`

## pseudocode

```c
__int64 __fastcall UWFUpdateAgent::printTitleAndKBNumber(
        UWFUpdateAgent *this,
        struct IUpdate *a2,
        unsigned __int16 *a3,
        int a4)
{
  struct IUpdateVtbl *lpVtbl; // rax
  __int64 result; // rax
  struct IUpdateVtbl *v8; // rax
  int v9; // edi
  void (*v10)(void); // rax
  unsigned int i; // esi
  BSTR bstrString[2]; // [rsp+20h] [rbp-10h] BYREF
  UWFUpdateAgent *v13; // [rsp+60h] [rbp+30h] BYREF
  wchar_t *Source; // [rsp+70h] [rbp+40h] BYREF
  int v15; // [rsp+78h] [rbp+48h] BYREF

  v15 = a4;
  v13 = this;
  if ( !a3 || !a2 )
    return 2147500037LL;
  lpVtbl = a2->lpVtbl;
  Source = 0;
  result = ((__int64 (__fastcall *)(struct IUpdate *, wchar_t **))lpVtbl->get_Title)(a2, &Source);
  if ( (int)result >= 0 )
  {
    swprintf_s(a3, 0x100u, L" ");
    wcscat_s(a3, 0x100u, Source);
    SysFreeString(Source);
    v8 = a2->lpVtbl;
    v13 = 0;
    result = ((__int64 (__fastcall *)(struct IUpdate *, UWFUpdateAgent **))v8->get_KBArticleIDs)(a2, &v13);
    if ( (int)result >= 0 )
    {
      if ( v13 )
      {
        v15 = 0;
        v9 = (*(__int64 (__fastcall **)(UWFUpdateAgent *, int *))(*(_QWORD *)v13 + 80LL))(v13, &v15);
        if ( v9 >= 0 )
        {
          wcscat_s(a3, 0x100u, L" ");
          wcscat_s(a3, 0x100u, L"KBNumbers  ");
          for ( i = 0; (int)i < v15; ++i )
          {
            bstrString[0] = 0;
            v9 = (*(__int64 (__fastcall **)(UWFUpdateAgent *, _QWORD, BSTR *))(*(_QWORD *)v13 + 56LL))(
                   v13,
                   i,
                   bstrString);
            if ( v9 < 0 )
              break;
            wcscat_s(a3, 0x100u, bstrString[0]);
            wcscat_s(a3, 0x100u, L" ");
            SysFreeString(bstrString[0]);
          }
          v10 = *(void (**)(void))(*(_QWORD *)v13 + 16LL);
        }
        else
        {
          v10 = *(void (**)(void))(*(_QWORD *)v13 + 16LL);
        }
        v10();
        return (unsigned int)v9;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004f50  mov     [rsp-28h+arg_18], r9d
0x180004f55  mov     [rsp-28h+arg_0], rcx
0x180004f5a  push    rbp
0x180004f5b  push    rbx
0x180004f5c  push    rsi
0x180004f5d  push    rdi
0x180004f5e  push    r15
0x180004f60  mov     rbp, rsp
0x180004f63  sub     rsp, 30h
0x180004f67  mov     rbx, r8
0x180004f6a  mov     rdi, rdx
0x180004f6d  test    r8, r8
0x180004f70  jz      loc_1800050D1
0x180004f76  test    rdx, rdx
0x180004f79  jz      loc_1800050D1
0x180004f7f  mov     rax, [rdx]
0x180004f82  mov     rcx, rdi
0x180004f85  lea     rdx, [rbp+Source]
0x180004f89  mov     [rbp+Source], 0
0x180004f91  mov     rax, [rax+38h]
0x180004f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f9a  test    eax, eax
0x180004f9c  js      loc_1800050D6
0x180004fa2  mov     r15d, 100h
0x180004fa8  lea     r8, asc_18000A2D0; " "
0x180004faf  mov     edx, r15d; BufferCount
0x180004fb2  mov     rcx, rbx; Buffer
0x180004fb5  call    cs:__imp_swprintf_s
0x180004fbb  mov     r8, [rbp+Source]; Source
0x180004fbf  mov     edx, r15d; SizeInWords
0x180004fc2  mov     rcx, rbx; Destination
0x180004fc5  call    cs:__imp_wcscat_s
0x180004fcb  mov     rcx, [rbp+Source]; bstrString
0x180004fcf  call    cs:__imp_SysFreeString
0x180004fd5  mov     rax, [rdi]
0x180004fd8  lea     rdx, [rbp+arg_0]
0x180004fdc  mov     rcx, rdi
0x180004fdf  mov     [rbp+arg_0], 0
0x180004fe7  mov     rax, [rax+170h]
0x180004fee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ff3  test    eax, eax
0x180004ff5  js      loc_1800050D6
0x180004ffb  mov     rcx, [rbp+arg_0]
0x180004fff  test    rcx, rcx
0x180005002  jz      loc_1800050D6
0x180005008  mov     [rbp+arg_18], 0
0x18000500f  lea     rdx, [rbp+arg_18]
0x180005013  mov     rax, [rcx]
0x180005016  mov     rax, [rax+50h]
0x18000501a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000501f  mov     edi, eax
0x180005021  test    eax, eax
0x180005023  jns     short loc_18000503C
0x180005025  mov     rcx, [rbp+arg_0]
0x180005029  mov     rdx, [rcx]
0x18000502c  mov     rax, [rdx+10h]
0x180005030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005035  mov     eax, edi
0x180005037  jmp     loc_1800050D6
0x18000503c  lea     r8, asc_18000A2D0; " "
0x180005043  mov     rdx, r15; SizeInWords
0x180005046  mov     rcx, rbx; Destination
0x180005049  call    cs:__imp_wcscat_s
0x18000504f  lea     r8, aKbnumbers; "KBNumbers  "
0x180005056  mov     rdx, r15; SizeInWords
0x180005059  mov     rcx, rbx; Destination
0x18000505c  call    cs:__imp_wcscat_s
0x180005062  xor     esi, esi
0x180005064  cmp     [rbp+arg_18], esi
0x180005067  jle     short loc_1800050C1
0x180005069  mov     rcx, [rbp+arg_0]
0x18000506d  lea     r8, [rbp+bstrString]
0x180005071  mov     [rbp+bstrString], 0
0x180005079  mov     edx, esi
0x18000507b  mov     rax, [rcx]
0x18000507e  mov     rax, [rax+38h]
0x180005082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005087  mov     edi, eax
0x180005089  test    eax, eax
0x18000508b  js      short loc_1800050C1
0x18000508d  mov     r8, [rbp+bstrString]; Source
0x180005091  mov     rdx, r15; SizeInWords
0x180005094  mov     rcx, rbx; Destination
0x180005097  call    cs:__imp_wcscat_s
0x18000509d  lea     r8, asc_18000A2D0; " "
0x1800050a4  mov     rdx, r15; SizeInWords
0x1800050a7  mov     rcx, rbx; Destination
0x1800050aa  call    cs:__imp_wcscat_s
0x1800050b0  mov     rcx, [rbp+bstrString]; bstrString
0x1800050b4  call    cs:__imp_SysFreeString
0x1800050ba  inc     esi
0x1800050bc  cmp     esi, [rbp+arg_18]
0x1800050bf  jl      short loc_180005069
0x1800050c1  mov     rcx, [rbp+arg_0]
0x1800050c5  mov     rax, [rcx]
0x1800050c8  mov     rax, [rax+10h]
0x1800050cc  jmp     loc_180005030
0x1800050d1  mov     eax, 80004005h
0x1800050d6  add     rsp, 30h
0x1800050da  pop     r15
0x1800050dc  pop     rdi
0x1800050dd  pop     rsi
0x1800050de  pop     rbx
0x1800050df  pop     rbp
0x1800050e0  retn
```
