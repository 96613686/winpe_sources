# _com_issue_errorex(long,IUnknown *,_GUID const &)

- ea: `0x18004115c`
- end: `0x1800411ee`
- name: `?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z`
- size: `146`
- prototype: `void __fastcall __noreturn(int, struct IUnknown *, const struct _GUID *)`
- caller_count: `22`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180047c10`
- `0x18004bdbc`
- `0x18004d190`
- `0x18004d1ec`
- `0x18004d24c`
- `0x18004d294`
- `0x18004d314`
- `0x18004d370`
- `0x18004d3d0`
- `0x18004d434`
- `0x18004e16c`
- `0x180050e80`
- `0x1800510f8`
- `0x180051d9c`
- `0x180051e00`
- `0x180051e7c`
- `0x18005216c`
- `0x1800521d4`
- `0x1800524fc`
- `0x180052588`
- `0x180053bd0`
- `0x180054194`

## callees

- `0x18004115c`
- `0x1800412c8`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_GetErrorInfo` at `0x1800411ce`
- `OLEAUT32!__imp_GetErrorInfo` at `0x1800411ce`

## pseudocode

```c
void __fastcall __noreturn _com_issue_errorex(int a1, struct IUnknown *a2, const struct _GUID *a3)
{
  struct IErrorInfo *v5; // rdx
  struct IUnknownVtbl *lpVtbl; // rax
  int v8; // ebx
  __int64 v9; // [rsp+38h] [rbp+10h] BYREF
  IErrorInfo *pperrinfo; // [rsp+48h] [rbp+20h] BYREF

  v5 = 0;
  pperrinfo = 0;
  if ( a2 )
  {
    lpVtbl = a2->lpVtbl;
    v9 = 0;
    if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))lpVtbl->QueryInterface)(
           a2,
           &GUID_df0b3d60_548f_101b_8e65_08002b2bd119,
           &v9) < 0
      || (v8 = (*(__int64 (__fastcall **)(__int64, const struct _GUID *))(*(_QWORD *)v9 + 24LL))(v9, a3),
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9),
          v8)
      || !GetErrorInfo(0, &pperrinfo) )
    {
      v5 = pperrinfo;
    }
    else
    {
      v5 = 0;
      pperrinfo = 0;
    }
  }
  _com_raise_error(a1, v5);
}

```

## disassembly

```asm
0x18004115c  mov     r11, rsp
0x18004115f  mov     [r11+8], rbx
0x180041163  push    rdi
0x180041164  sub     rsp, 20h
0x180041168  mov     r9, rdx
0x18004116b  mov     rbx, r8
0x18004116e  xor     edx, edx
0x180041170  mov     edi, ecx
0x180041172  mov     [r11+20h], rdx
0x180041176  test    r9, r9
0x180041179  jz      short loc_1800411E6
0x18004117b  mov     rax, [r9]
0x18004117e  lea     r8, [r11+10h]
0x180041182  mov     [r11+10h], rdx
0x180041186  mov     rcx, r9
0x180041189  lea     rdx, _GUID_df0b3d60_548f_101b_8e65_08002b2bd119
0x180041190  mov     rax, [rax]
0x180041193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041198  test    eax, eax
0x18004119a  js      short loc_1800411E1
0x18004119c  mov     rcx, [rsp+28h+arg_8]
0x1800411a1  mov     rdx, rbx
0x1800411a4  mov     rax, [rcx]
0x1800411a7  mov     rax, [rax+18h]
0x1800411ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800411b0  mov     rcx, [rsp+28h+arg_8]
0x1800411b5  mov     ebx, eax
0x1800411b7  mov     rdx, [rcx]
0x1800411ba  mov     rax, [rdx+10h]
0x1800411be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800411c3  test    ebx, ebx
0x1800411c5  jnz     short loc_1800411E1
0x1800411c7  lea     rdx, [rsp+28h+pperrinfo]; pperrinfo
0x1800411cc  xor     ecx, ecx; dwReserved
0x1800411ce  call    cs:__imp_GetErrorInfo
0x1800411d4  test    eax, eax
0x1800411d6  jz      short loc_1800411E1
0x1800411d8  xor     edx, edx
0x1800411da  mov     [rsp+28h+pperrinfo], rdx
0x1800411df  jmp     short loc_1800411E6
0x1800411e1  mov     rdx, [rsp+28h+pperrinfo]; struct IErrorInfo *
0x1800411e6  mov     ecx, edi; int
0x1800411e8  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
```
