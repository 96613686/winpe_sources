# BasepSxsIsStatusFileNotFoundEtc

- ea: `0x1800042b0`
- end: `0x180004302`
- name: `BasepSxsIsStatusFileNotFoundEtc`
- size: `82`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800028d0`
- `0x180002d40`
- `0x180003310`

## callees

- `0x1800042b0`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800042e2`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800042e2`

## pseudocode

```c
_BOOL8 __fastcall BasepSxsIsStatusFileNotFoundEtc(NTSTATUS a1)
{
  _BOOL8 result; // rax
  unsigned __int64 v2; // rax
  __int64 v3; // rdx
  ULONG v4; // eax

  result = 0;
  if ( a1 < 0 )
  {
    v2 = (unsigned int)(a1 + 1073741809);
    if ( (unsigned int)v2 <= 0x2B )
    {
      v3 = 0x82000000001LL;
      if ( _bittest64(&v3, v2) )
        return 1;
    }
    v4 = RtlNtStatusToDosErrorNoTeb(a1);
    if ( v4 == 53 || v4 - 2 <= 1 || v4 == 67 )
      return 1;
  }
  return result;
}

```

## disassembly

```asm
0x1800042b0  sub     rsp, 28h
0x1800042b4  test    ecx, ecx
0x1800042b6  js      short loc_1800042C0
0x1800042b8  xor     eax, eax
0x1800042ba  add     rsp, 28h
0x1800042be  retn
0x1800042c0  lea     eax, [rcx+3FFFFFF1h]
0x1800042c6  cmp     eax, 2Bh ; '+'
0x1800042c9  ja      short loc_1800042E2
0x1800042cb  mov     rdx, 82000000001h
0x1800042d5  bt      rdx, rax
0x1800042d9  jnb     short loc_1800042E2
0x1800042db  mov     eax, 1
0x1800042e0  jmp     short loc_1800042BA
0x1800042e2  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800042e9  nop     dword ptr [rax+rax+00h]
0x1800042ee  cmp     eax, 35h ; '5'
0x1800042f1  jz      short loc_1800042DB
0x1800042f3  lea     ecx, [rax-2]
0x1800042f6  cmp     ecx, 1
0x1800042f9  jbe     short loc_1800042DB
0x1800042fb  cmp     eax, 43h ; 'C'
0x1800042fe  jnz     short loc_1800042B8
0x180004300  jmp     short loc_1800042DB
```
