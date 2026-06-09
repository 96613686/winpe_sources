# WriteLog(LogLevel,char const *,...)

- ea: `0x14000f684`
- end: `0x14000f7de`
- name: `?WriteLog@@YAXW4LogLevel@@PEBDZZ`
- size: `346`
- prototype: `void __high(enum LogLevel, const char *, ...)`
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x1400099e0`
- `0x140009ee0`
- `0x14000a300`
- `0x14000b550`
- `0x14000b970`
- `0x14000bdf0`
- `0x14000d8a8`
- `0x14000d9c4`
- `0x14000dd90`
- `0x14000df1c`
- `0x14000e1d0`
- `0x14000e488`
- `0x14000e778`
- `0x14001f130`
- `0x14001f288`

## callees

- `0x14000f684`
- `0x14000fd40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000f7ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f7ca`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000f6db`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000f6db`
- `ntoskrnl!strnlen` at `0x14000f6b3`
- `ntoskrnl!strnlen` at `0x14000f6b3`

## pseudocode

```c
void WriteLog(_QWORD a1, const char *a2, ...)
{
  size_t v2; // rax
  size_t v3; // rbx
  _BYTE *PoolWithTag; // rax
  _BYTE *v5; // rdi
  _BYTE *v6; // rcx
  const char *v7; // r8
  __int64 v8; // r9
  __int64 v9; // rax
  size_t v10; // rdx
  _BYTE *v11; // rax
  size_t v12; // rax
  _BYTE *v13; // rdx
  size_t v14; // rdx
  __int16 *v15; // rax
  _BYTE *v16; // r8
  size_t i; // rbx
  _BYTE *v18; // rax
  __int16 v19; // [rsp+20h] [rbp-28h] BYREF

  if ( a2 )
  {
    v19 = 10;
    v2 = strnlen(a2, 0xFFFFFFFFFFFFFFFFuLL);
    v3 = v2 + 2;
    if ( v2 < 0xFFFFFFFFFFFFFFFEuLL && v2 != 0 )
    {
      PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1025, v2 + 2, 0x6E6D7377u);
      v5 = PoolWithTag;
      if ( PoolWithTag )
      {
        v6 = PoolWithTag;
        if ( !ExPoolZeroingNativelySupported )
        {
          memset(PoolWithTag, 0, v3);
          v6 = v5;
        }
        if ( v3 <= 0x7FFFFFFF )
        {
          v7 = a2;
          v8 = 2147483646;
          v9 = 2147483646;
          v10 = v3;
          do
          {
            if ( !v9 )
              break;
            if ( !*v7 )
              break;
            *v5++ = *v7++;
            --v9;
            --v10;
          }
          while ( v10 );
          v11 = v5 - 1;
          if ( v10 )
            v11 = v5;
          *v11 = 0;
          if ( v10 && v3 - 1 <= 0x7FFFFFFE )
          {
            v12 = v3;
            v13 = v6;
            while ( *v13 )
            {
              ++v13;
              if ( !--v12 )
              {
                v14 = 0;
                goto LABEL_21;
              }
            }
            v14 = v3 - v12;
LABEL_21:
            if ( v12 )
            {
              v15 = &v19;
              v16 = &v6[v14];
              for ( i = v3 - v14; i; --i )
              {
                if ( !v8 )
                  break;
                if ( !*(_BYTE *)v15 )
                  break;
                *v16 = *(_BYTE *)v15;
                v15 = (__int16 *)((char *)v15 + 1);
                ++v16;
                --v8;
              }
              v18 = v16 - 1;
              if ( i )
                v18 = v16;
              *v18 = 0;
            }
          }
        }
        else
        {
          *v6 = 0;
        }
        ExFreePoolWithTag(v6, 0x6E6D7377u);
      }
    }
  }
}

```

## disassembly

```asm
0x14000f684  test    rdx, rdx
0x14000f687  jz      locret_14000F7DC
0x14000f68d  mov     [rsp+arg_8], rdx
0x14000f692  mov     [rsp+arg_10], r8
0x14000f697  mov     [rsp+arg_18], r9
0x14000f69c  push    rbx
0x14000f69d  push    rdi
0x14000f69e  sub     rsp, 38h
0x14000f6a2  mov     rax, rdx
0x14000f6a5  mov     [rsp+48h+var_28], 0Ah
0x14000f6ac  mov     rcx, rax; Str
0x14000f6af  or      rdx, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14000f6b3  call    cs:__imp_strnlen
0x14000f6ba  nop     dword ptr [rax+rax+00h]
0x14000f6bf  lea     rbx, [rax+2]
0x14000f6c3  cmp     rbx, 2
0x14000f6c7  jbe     loc_14000F7D6
0x14000f6cd  mov     r8d, 6E6D7377h; Tag
0x14000f6d3  mov     rdx, rbx; NumberOfBytes
0x14000f6d6  mov     ecx, 401h; PoolType
0x14000f6db  call    cs:__imp_ExAllocatePoolWithTag
0x14000f6e2  nop     dword ptr [rax+rax+00h]
0x14000f6e7  mov     rdi, rax
0x14000f6ea  test    rax, rax
0x14000f6ed  jz      loc_14000F7D6
0x14000f6f3  cmp     cs:ExPoolZeroingNativelySupported, 0
0x14000f6fa  mov     rcx, rax; void *
0x14000f6fd  jnz     short loc_14000F70C
0x14000f6ff  mov     r8, rbx; Size
0x14000f702  xor     edx, edx; Val
0x14000f704  call    memset
0x14000f709  mov     rcx, rdi; P
0x14000f70c  cmp     rbx, 7FFFFFFFh
0x14000f713  jbe     short loc_14000F71D
0x14000f715  mov     byte ptr [rcx], 0
0x14000f718  jmp     loc_14000F7C5
0x14000f71d  mov     r8, [rsp+48h+arg_8]
0x14000f722  mov     r9d, 7FFFFFFEh
0x14000f728  mov     eax, r9d
0x14000f72b  mov     rdx, rbx
0x14000f72e  mov     r11d, 1
0x14000f734  test    rax, rax
0x14000f737  jz      short loc_14000F752
0x14000f739  mov     r10b, [r8]
0x14000f73c  test    r10b, r10b
0x14000f73f  jz      short loc_14000F752
0x14000f741  mov     [rdi], r10b
0x14000f744  add     r8, r11
0x14000f747  add     rdi, r11
0x14000f74a  sub     rax, r11
0x14000f74d  sub     rdx, r11
0x14000f750  jnz     short loc_14000F734
0x14000f752  test    rdx, rdx
0x14000f755  lea     rax, [rdi-1]
0x14000f759  cmovnz  rax, rdi
0x14000f75d  mov     byte ptr [rax], 0
0x14000f760  jz      short loc_14000F7C5
0x14000f762  lea     rax, [rbx-1]
0x14000f766  cmp     rax, r9
0x14000f769  ja      short loc_14000F7C5
0x14000f76b  mov     rax, rbx
0x14000f76e  mov     rdx, rcx
0x14000f771  cmp     byte ptr [rdx], 0
0x14000f774  jz      short loc_14000F782
0x14000f776  add     rdx, r11
0x14000f779  sub     rax, r11
0x14000f77c  jnz     short loc_14000F771
0x14000f77e  xor     edx, edx
0x14000f780  jmp     short loc_14000F788
0x14000f782  mov     rdx, rbx
0x14000f785  sub     rdx, rax
0x14000f788  test    rax, rax
0x14000f78b  jz      short loc_14000F7C5
0x14000f78d  lea     rax, [rsp+48h+var_28]
0x14000f792  lea     r8, [rdx+rcx]
0x14000f796  sub     rbx, rdx
0x14000f799  jz      short loc_14000F7B7
0x14000f79b  test    r9, r9
0x14000f79e  jz      short loc_14000F7B7
0x14000f7a0  mov     dl, [rax]
0x14000f7a2  test    dl, dl
0x14000f7a4  jz      short loc_14000F7B7
0x14000f7a6  mov     [r8], dl
0x14000f7a9  add     rax, r11
0x14000f7ac  add     r8, r11
0x14000f7af  sub     r9, r11
0x14000f7b2  sub     rbx, r11
0x14000f7b5  jnz     short loc_14000F79B
0x14000f7b7  test    rbx, rbx
0x14000f7ba  lea     rax, [r8-1]
0x14000f7be  cmovnz  rax, r8
0x14000f7c2  mov     byte ptr [rax], 0
0x14000f7c5  mov     edx, 6E6D7377h; Tag
0x14000f7ca  call    cs:__imp_ExFreePoolWithTag
0x14000f7d1  nop     dword ptr [rax+rax+00h]
0x14000f7d6  add     rsp, 38h
0x14000f7da  pop     rdi
0x14000f7db  pop     rbx
0x14000f7dc  retn
```
