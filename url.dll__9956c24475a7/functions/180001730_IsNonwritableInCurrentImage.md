# _IsNonwritableInCurrentImage

- ea: `0x180001730`
- end: `0x18000177a`
- name: `_IsNonwritableInCurrentImage`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001050`

## callees

- `0x1800016e0`
- `0x180001730`
- `0x180001780`

## pseudocode

```c
__int64 __fastcall IsNonwritableInCurrentImage(__int64 a1)
{
  __int64 result; // rax

  result = ValidateImageBase(&_ImageBase);
  if ( (_DWORD)result )
  {
    result = FindPESection(&_ImageBase, a1 - (_QWORD)&_ImageBase);
    if ( result )
      return *(_DWORD *)(result + 36) >= 0;
  }
  return result;
}

```

## disassembly

```asm
0x180001730  mov     [rsp+arg_0], rbx
0x180001735  push    rdi
0x180001736  sub     rsp, 20h
0x18000173a  mov     rbx, rcx
0x18000173d  lea     rdi, __ImageBase
0x180001744  mov     rcx, rdi
0x180001747  call    _ValidateImageBase
0x18000174c  test    eax, eax
0x18000174e  jz      short loc_18000176F
0x180001750  sub     rbx, rdi
0x180001753  mov     rdx, rbx
0x180001756  mov     rcx, rdi
0x180001759  call    _FindPESection
0x18000175e  test    rax, rax
0x180001761  jz      short loc_18000176F
0x180001763  mov     eax, [rax+24h]
0x180001766  not     eax
0x180001768  shr     eax, 1Fh
0x18000176b  jmp     short loc_18000176F
0x18000176d  xor     eax, eax
0x18000176f  mov     rbx, [rsp+28h+arg_0]
0x180001774  add     rsp, 20h
0x180001778  pop     rdi
0x180001779  retn
0x180002520  push    rbp
0x180002522  sub     rsp, 20h
0x180002526  mov     rbp, rdx
0x180002529  mov     rax, [rcx]
0x18000252c  xor     ecx, ecx
0x18000252e  cmp     dword ptr [rax], 0C0000005h
0x180002534  setz    cl
0x180002537  mov     eax, ecx
0x180002539  add     rsp, 20h
0x18000253d  pop     rbp
0x18000253e  retn
```
