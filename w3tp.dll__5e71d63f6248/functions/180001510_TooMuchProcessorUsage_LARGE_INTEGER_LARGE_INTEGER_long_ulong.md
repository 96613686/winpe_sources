# TooMuchProcessorUsage(_LARGE_INTEGER,_LARGE_INTEGER,long,ulong)

- ea: `0x180001510`
- end: `0x180001584`
- name: `?TooMuchProcessorUsage@@YAHT_LARGE_INTEGER@@0JK@Z`
- size: `116`
- prototype: `__int64 __fastcall(union _LARGE_INTEGER, union _LARGE_INTEGER, int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001450`

## callees

- `0x180001510`
- `0x180001590`

## pseudocode

```c
_BOOL8 __fastcall TooMuchProcessorUsage(union _LARGE_INTEGER a1, union _LARGE_INTEGER a2, int a3)
{
  LONGLONG v6; // rcx
  union _LARGE_INTEGER v8; // [rsp+20h] [rbp-38h] BYREF
  union _LARGE_INTEGER v9; // [rsp+28h] [rbp-30h] BYREF

  v9.QuadPart = 0;
  v8.QuadPart = 0;
  if ( (int)GetProcessorInformation(&v9, &v8, g_dwNumProcs) < 0 )
    return 1;
  if ( v8.QuadPart == a2.QuadPart )
    LODWORD(v6) = 100;
  else
    v6 = 100 * (v9.QuadPart - a1.QuadPart) / (v8.QuadPart - a2.QuadPart);
  return (int)v6 >= a3;
}

```

## disassembly

```asm
0x180001510  push    rbx
0x180001512  push    rbp
0x180001513  push    rsi
0x180001514  push    rdi
0x180001515  sub     rsp, 38h
0x180001519  mov     esi, r8d
0x18000151c  mov     rbx, rdx
0x18000151f  mov     r8d, cs:?g_dwNumProcs@@3KA; unsigned int
0x180001526  lea     rdx, [rsp+58h+var_38]; union _LARGE_INTEGER *
0x18000152b  mov     rdi, rcx
0x18000152e  xor     ebp, ebp
0x180001530  lea     rcx, [rsp+58h+var_30]; union _LARGE_INTEGER *
0x180001535  mov     qword ptr [rsp+58h+var_30], rbp
0x18000153a  mov     qword ptr [rsp+58h+var_38], rbp
0x18000153f  call    ?GetProcessorInformation@@YAJPEAT_LARGE_INTEGER@@0K@Z; GetProcessorInformation(_LARGE_INTEGER *,_LARGE_INTEGER *,ulong)
0x180001544  test    eax, eax
0x180001546  js      short loc_180001576
0x180001548  mov     rcx, qword ptr [rsp+58h+var_38]
0x18000154d  sub     rcx, rbx
0x180001550  jnz     short loc_180001559
0x180001552  mov     ecx, 64h ; 'd'
0x180001557  jmp     short loc_18000156D
0x180001559  mov     rax, qword ptr [rsp+58h+var_30]
0x18000155e  sub     rax, rdi
0x180001561  imul    rax, 64h ; 'd'
0x180001565  cqo
0x180001567  idiv    rcx
0x18000156a  mov     rcx, rax
0x18000156d  cmp     ecx, esi
0x18000156f  mov     eax, ebp
0x180001571  setnl   al
0x180001574  jmp     short loc_18000157B
0x180001576  mov     eax, 1
0x18000157b  add     rsp, 38h
0x18000157f  pop     rdi
0x180001580  pop     rsi
0x180001581  pop     rbp
0x180001582  pop     rbx
0x180001583  retn
```
