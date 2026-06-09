# AllocSplStr(ushort const *)

- ea: `0x180002ee0`
- end: `0x180002fb4`
- name: `?AllocSplStr@@YAPEAGPEBG@Z`
- size: `212`
- prototype: `unsigned __int16 *__fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003390`

## callees

- `0x180002ee0`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180002f30`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180002f30`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180002fa5`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180002fa5`

## pseudocode

```c
unsigned __int16 *__fastcall AllocSplStr(const unsigned __int16 *a1)
{
  const unsigned __int16 *v1; // rdi
  __int64 v2; // rdx
  const unsigned __int16 *v3; // rax
  unsigned __int16 *result; // rax
  __int64 v5; // rbx
  unsigned __int16 *v6; // r9
  unsigned __int64 v7; // rdx
  __int64 v8; // rcx
  unsigned __int16 *v9; // rcx

  v1 = a1;
  if ( !a1 )
    return 0;
  v2 = 0x7FFFFFFF;
  v3 = a1;
  do
  {
    if ( !*v3 )
      break;
    ++v3;
    --v2;
  }
  while ( v2 );
  result = 0;
  v5 = 0x7FFFFFFF - v2;
  if ( v2 )
  {
    result = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v5 + 2);
    v6 = result;
    if ( result )
    {
      v7 = v5 + 1;
      if ( v5 != -1 )
      {
        if ( v7 > 0x7FFFFFFF )
        {
          *result = 0;
        }
        else
        {
          v8 = 2147483646;
          do
          {
            if ( !v8 )
              break;
            if ( !*v1 )
              break;
            *result++ = *v1++;
            --v8;
            --v7;
          }
          while ( v7 );
          v9 = result - 1;
          if ( v7 )
            v9 = result;
          *v9 = 0;
          if ( v7 )
            return v6;
        }
      }
      LocalFree(v6);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002ee0  push    rdi
0x180002ee2  sub     rsp, 20h
0x180002ee6  mov     rdi, rcx
0x180002ee9  xor     ecx, ecx
0x180002eeb  test    rdi, rdi
0x180002eee  jz      loc_180002FAF
0x180002ef4  mov     [rsp+28h+arg_0], rbx
0x180002ef9  mov     edx, 7FFFFFFFh
0x180002efe  mov     rax, rdi
0x180002f01  cmp     [rax], cx
0x180002f04  jz      short loc_180002F10
0x180002f06  add     rax, 2
0x180002f0a  sub     rdx, 1
0x180002f0e  jnz     short loc_180002F01
0x180002f10  xor     eax, eax
0x180002f12  mov     ebx, 7FFFFFFFh
0x180002f17  sub     rbx, rdx
0x180002f1a  test    rdx, rdx
0x180002f1d  cmovz   rbx, rax
0x180002f21  jz      short loc_180002F91
0x180002f23  lea     rdx, ds:2[rbx*2]; uBytes
0x180002f2b  mov     ecx, 40h ; '@'; uFlags
0x180002f30  call    cs:__imp_LocalAlloc
0x180002f36  mov     r9, rax
0x180002f39  test    rax, rax
0x180002f3c  jz      short loc_180002F91
0x180002f3e  lea     rdx, [rbx+1]
0x180002f42  test    rdx, rdx
0x180002f45  jz      short loc_180002FA2
0x180002f47  cmp     rdx, 7FFFFFFFh
0x180002f4e  ja      short loc_180002F9C
0x180002f50  mov     ecx, 7FFFFFFEh
0x180002f55  test    rcx, rcx
0x180002f58  jz      short loc_180002F79
0x180002f5a  movzx   r8d, word ptr [rdi]
0x180002f5e  test    r8w, r8w
0x180002f62  jz      short loc_180002F79
0x180002f64  mov     [rax], r8w
0x180002f68  add     rdi, 2
0x180002f6c  add     rax, 2
0x180002f70  dec     rcx
0x180002f73  sub     rdx, 1
0x180002f77  jnz     short loc_180002F55
0x180002f79  test    rdx, rdx
0x180002f7c  lea     rcx, [rax-2]
0x180002f80  cmovnz  rcx, rax
0x180002f84  xor     eax, eax
0x180002f86  mov     [rcx], ax
0x180002f89  test    rdx, rdx
0x180002f8c  jz      short loc_180002FA2
0x180002f8e  mov     rax, r9
0x180002f91  mov     rbx, [rsp+28h+arg_0]
0x180002f96  add     rsp, 20h
0x180002f9a  pop     rdi
0x180002f9b  retn
0x180002f9c  xor     eax, eax
0x180002f9e  mov     [r9], ax
0x180002fa2  mov     rcx, r9; hMem
0x180002fa5  call    cs:__imp_LocalFree
0x180002fab  xor     eax, eax
0x180002fad  jmp     short loc_180002F91
0x180002faf  mov     rax, rcx
0x180002fb2  jmp     short loc_180002F96
```
