# BuildPathMulti

- ea: `0x1800153c8`
- end: `0x18001546e`
- name: `BuildPathMulti`
- size: `166`
- prototype: `wchar_t *(unsigned int, const wchar_t *, const wchar_t *, ...)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002b98`
- `0x180004428`
- `0x180004844`
- `0x1800051d8`
- `0x18000548c`
- `0x18000deec`

## callees

- `0x1800151f0`
- `0x1800153c8`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180015455`
- `ntdll!RtlFreeHeap` at `0x180015455`

## pseudocode

```c
wchar_t *BuildPathMulti(unsigned int a1, const wchar_t *a2, const wchar_t *a3, ...)
{
  unsigned int v3; // edi
  const wchar_t **v5; // rsi
  wchar_t *i; // rbx
  const wchar_t *v7; // rdx
  wchar_t *v8; // rbp
  va_list va; // [rsp+78h] [rbp+20h] BYREF

  va_start(va, a3);
  v3 = 2;
  if ( a1 >= 2 )
  {
    va_copy((va_list)v5, va);
    for ( i = BuildPath(a2, a3); i; ++v3 )
    {
      if ( v3 >= a1 )
        break;
      v7 = *v5++;
      v8 = i;
      i = BuildPath(i, v7);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
    }
    return i;
  }
  else
  {
    NtCurrentTeb()->LastErrorValue = 87;
    return 0;
  }
}

```

## disassembly

```asm
0x1800153c8  mov     rax, rsp
0x1800153cb  mov     [rax+8], ecx
0x1800153ce  mov     [rax+10h], rdx
0x1800153d2  mov     [rax+18h], r8
0x1800153d6  mov     [rax+20h], r9
0x1800153da  push    rbx
0x1800153db  push    rbp
0x1800153dc  push    rsi
0x1800153dd  push    rdi
0x1800153de  sub     rsp, 38h
0x1800153e2  mov     edi, 2
0x1800153e7  mov     qword ptr [rax-38h], 0
0x1800153ef  lea     rax, [rax+10h]
0x1800153f3  cmp     ecx, edi
0x1800153f5  jnb     short loc_18001540B
0x1800153f7  mov     rax, gs:30h
0x180015400  mov     dword ptr [rax+68h], 57h ; 'W'
0x180015407  xor     eax, eax
0x180015409  jmp     short loc_180015465
0x18001540b  mov     rcx, [rax]; pszSrc
0x18001540e  lea     rsi, [rax+10h]
0x180015412  mov     rdx, [rsi-8]; STRSAFE_PCNZWCH
0x180015416  call    BuildPath
0x18001541b  mov     rbx, rax
0x18001541e  test    rax, rax
0x180015421  jz      short loc_180015462
0x180015423  cmp     edi, [rsp+58h+arg_0]
0x180015427  jnb     short loc_180015462
0x180015429  mov     rdx, [rsi]; STRSAFE_PCNZWCH
0x18001542c  add     rsi, 8
0x180015430  mov     rcx, rbx; pszSrc
0x180015433  mov     rbp, rbx
0x180015436  call    BuildPath
0x18001543b  mov     rbx, rax
0x18001543e  test    rbp, rbp
0x180015441  jz      short loc_18001545B
0x180015443  mov     rcx, gs:60h
0x18001544c  mov     r8, rbp; P
0x18001544f  xor     edx, edx; Flags
0x180015451  mov     rcx, [rcx+30h]; HeapHandle
0x180015455  call    cs:__imp_RtlFreeHeap
0x18001545b  inc     edi
0x18001545d  test    rbx, rbx
0x180015460  jnz     short loc_180015423
0x180015462  mov     rax, rbx
0x180015465  add     rsp, 38h
0x180015469  pop     rdi
0x18001546a  pop     rsi
0x18001546b  pop     rbp
0x18001546c  pop     rbx
0x18001546d  retn
```
