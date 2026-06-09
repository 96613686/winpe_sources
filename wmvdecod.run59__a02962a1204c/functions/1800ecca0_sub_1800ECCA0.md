# sub_1800ECCA0

- ea: `0x1800ecca0`
- end: `0x1800ecd60`
- name: `sub_1800ECCA0`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800edf30`

## callees

- `0x180057fe4`
- `0x1800695b4`
- `0x1800ecca0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800eccee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800eccee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800eccb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800eccce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ecd0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800eccb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800eccce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ecd0c`

## pseudocode

```c
__int64 __fastcall sub_1800ECCA0(__int64 a1, __int64 a2, unsigned int a3)
{
  void *v6; // rcx
  LPVOID v7; // rax
  int v8; // esi
  __int64 (__fastcall *v10)(__int64, __int64, _QWORD); // rbx

  CoTaskMemFree(*(LPVOID *)(a1 + 8));
  v6 = *(void **)(a1 + 16);
  *(_QWORD *)(a1 + 8) = 0;
  CoTaskMemFree(v6);
  *(_QWORD *)(a1 + 16) = 0;
  *(_DWORD *)(a1 + 24) = 0;
  v7 = CoTaskMemAlloc(0x110u);
  *(_QWORD *)(a1 + 16) = v7;
  if ( v7 )
  {
    v10 = (__int64 (__fastcall *)(__int64, __int64, _QWORD))sub_1800695B4(word_18025E7DA);
    v8 = v10(a1, a2, a3);
    sub_180057FE4(v10);
    if ( v8 >= 0 )
    {
      *(_DWORD *)(a1 + 24) = 1;
      return (unsigned int)v8;
    }
  }
  else
  {
    v8 = -2147024882;
  }
  CoTaskMemFree(*(LPVOID *)(a1 + 16));
  *(_QWORD *)(a1 + 16) = 0;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800ecca0  push    rbx
0x1800ecca2  push    rbp
0x1800ecca3  push    rsi
0x1800ecca4  push    rdi
0x1800ecca5  sub     rsp, 28h
0x1800ecca9  mov     rdi, rcx
0x1800eccac  mov     esi, r8d
0x1800eccaf  mov     rcx, [rcx+8]; pv
0x1800eccb3  mov     rbp, rdx
0x1800eccb6  call    cs:CoTaskMemFree
0x1800eccbd  nop     dword ptr [rax+rax+00h]
0x1800eccc2  mov     rcx, [rdi+10h]; pv
0x1800eccc6  mov     qword ptr [rdi+8], 0
0x1800eccce  call    cs:CoTaskMemFree
0x1800eccd5  nop     dword ptr [rax+rax+00h]
0x1800eccda  mov     ecx, 110h; cb
0x1800eccdf  mov     qword ptr [rdi+10h], 0
0x1800ecce7  mov     dword ptr [rdi+18h], 0
0x1800eccee  call    cs:CoTaskMemAlloc
0x1800eccf5  nop     dword ptr [rax+rax+00h]
0x1800eccfa  mov     [rdi+10h], rax
0x1800eccfe  test    rax, rax
0x1800ecd01  jnz     short loc_1800ECD2C
0x1800ecd03  mov     esi, 8007000Eh
0x1800ecd08  mov     rcx, [rdi+10h]; pv
0x1800ecd0c  call    cs:CoTaskMemFree
0x1800ecd13  nop     dword ptr [rax+rax+00h]
0x1800ecd18  mov     qword ptr [rdi+10h], 0
0x1800ecd20  mov     eax, esi
0x1800ecd22  add     rsp, 28h
0x1800ecd26  pop     rdi
0x1800ecd27  pop     rsi
0x1800ecd28  pop     rbp
0x1800ecd29  pop     rbx
0x1800ecd2a  retn
0x1800ecd2c  lea     rcx, word_18025E7DA
0x1800ecd33  call    sub_1800695B4
0x1800ecd38  mov     r8d, esi
0x1800ecd3b  mov     rdx, rbp
0x1800ecd3e  mov     rcx, rdi
0x1800ecd41  mov     rbx, rax
0x1800ecd44  call    rax
0x1800ecd46  nop     dword ptr [rax]
0x1800ecd49  mov     rcx, rbx
0x1800ecd4c  mov     esi, eax
0x1800ecd4e  call    sub_180057FE4
0x1800ecd53  test    esi, esi
0x1800ecd55  js      short loc_1800ECD08
0x1800ecd57  mov     dword ptr [rdi+18h], 1
0x1800ecd5e  jmp     short loc_1800ECD20
```
