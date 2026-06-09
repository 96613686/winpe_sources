# XMLScrSite::CheckRuntimeSettings(void)

- ea: `0x14000bf40`
- end: `0x14000c047`
- name: `?CheckRuntimeSettings@XMLScrSite@@UEAAJXZ`
- size: `263`
- prototype: `__int64 __fastcall(XMLScrSite *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14000bf40`
- `0x140018010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14000bfa9`
- `OLEAUT32!__imp_SysAllocString` at `0x14000bfa9`

## pseudocode

```c
__int64 __fastcall XMLScrSite::CheckRuntimeSettings(XMLScrSite *this)
{
  __int64 v1; // rax
  int v3; // ebx
  BSTR v4; // rax
  __int16 v6; // [rsp+40h] [rbp+20h] BYREF
  __int64 v7; // [rsp+48h] [rbp+28h] BYREF
  __int64 v8; // [rsp+50h] [rbp+30h] BYREF

  v1 = *((_QWORD *)this + 2);
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(v1 + 624) + 128LL))(*(_QWORD *)(v1 + 624), &v7);
  if ( v3 >= 0 )
  {
    v3 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 88LL))(v7, &v8);
    if ( v3 >= 0 )
    {
      v4 = SysAllocString(L"?");
      v3 = (*(__int64 (__fastcall **)(__int64, BSTR, __int16 *))(*(_QWORD *)v8 + 80LL))(v8, v4, &v6);
      if ( v3 >= 0 )
      {
        if ( v6 )
        {
          v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 104LL))(v7);
          if ( v3 >= 0 )
          {
            v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 624LL) + 104LL))(
                   *(_QWORD *)(*((_QWORD *)this + 2) + 624LL),
                   0);
            if ( v3 >= 0 )
              v3 = 1;
          }
        }
      }
    }
  }
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14000bf40  mov     [rsp-18h+arg_18], rbx
0x14000bf45  push    rbp
0x14000bf46  push    rsi
0x14000bf47  push    rdi
0x14000bf48  mov     rbp, rsp
0x14000bf4b  sub     rsp, 20h
0x14000bf4f  mov     rax, [rcx+10h]
0x14000bf53  lea     rdx, [rbp+arg_8]
0x14000bf57  xor     esi, esi
0x14000bf59  mov     rdi, rcx
0x14000bf5c  mov     [rbp+arg_0], si
0x14000bf60  mov     [rbp+arg_8], rsi
0x14000bf64  mov     [rbp+arg_10], rsi
0x14000bf68  mov     rcx, [rax+270h]
0x14000bf6f  mov     rax, [rcx]
0x14000bf72  mov     rax, [rax+80h]
0x14000bf79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bf7e  mov     ebx, eax
0x14000bf80  test    eax, eax
0x14000bf82  js      loc_14000C00E
0x14000bf88  mov     rcx, [rbp+arg_8]
0x14000bf8c  lea     rdx, [rbp+arg_10]
0x14000bf90  mov     rax, [rcx]
0x14000bf93  mov     rax, [rax+58h]
0x14000bf97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bf9c  mov     ebx, eax
0x14000bf9e  test    eax, eax
0x14000bfa0  js      short loc_14000C00E
0x14000bfa2  lea     rcx, asc_14001C0BC; "?"
0x14000bfa9  call    cs:__imp_SysAllocString
0x14000bfaf  mov     rcx, [rbp+arg_10]
0x14000bfb3  lea     r8, [rbp+arg_0]
0x14000bfb7  mov     r9, rax
0x14000bfba  mov     rdx, [rcx]
0x14000bfbd  mov     rax, [rdx+50h]
0x14000bfc1  mov     rdx, r9
0x14000bfc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bfc9  mov     ebx, eax
0x14000bfcb  test    eax, eax
0x14000bfcd  js      short loc_14000C00E
0x14000bfcf  cmp     [rbp+arg_0], si
0x14000bfd3  jz      short loc_14000C00E
0x14000bfd5  mov     rcx, [rbp+arg_8]
0x14000bfd9  mov     rax, [rcx]
0x14000bfdc  mov     rax, [rax+68h]
0x14000bfe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bfe5  mov     ebx, eax
0x14000bfe7  test    eax, eax
0x14000bfe9  js      short loc_14000C00E
0x14000bfeb  mov     rax, [rdi+10h]
0x14000bfef  xor     edx, edx
0x14000bff1  mov     rcx, [rax+270h]
0x14000bff8  mov     rax, [rcx]
0x14000bffb  mov     rax, [rax+68h]
0x14000bfff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c004  mov     ebx, eax
0x14000c006  lea     eax, [rsi+1]
0x14000c009  test    ebx, ebx
0x14000c00b  cmovns  ebx, eax
0x14000c00e  mov     rcx, [rbp+arg_8]
0x14000c012  test    rcx, rcx
0x14000c015  jz      short loc_14000C023
0x14000c017  mov     rax, [rcx]
0x14000c01a  mov     rax, [rax+10h]
0x14000c01e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c023  mov     rcx, [rbp+arg_10]
0x14000c027  test    rcx, rcx
0x14000c02a  jz      short loc_14000C038
0x14000c02c  mov     rax, [rcx]
0x14000c02f  mov     rax, [rax+10h]
0x14000c033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c038  mov     eax, ebx
0x14000c03a  mov     rbx, [rsp+20h+arg_18]
0x14000c03f  add     rsp, 20h
0x14000c043  pop     rdi
0x14000c044  pop     rsi
0x14000c045  pop     rbp
0x14000c046  retn
```
