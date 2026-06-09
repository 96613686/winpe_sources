# I_ValidatePageHashesBlob

- ea: `0x1800457dc`
- end: `0x1800458d1`
- name: `I_ValidatePageHashesBlob`
- size: `245`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180044fe4`
- `0x180045a08`

## callees

- `0x1800457dc`
- `0x18004dd2c`

## import_xrefs

- `securekernel!RtlCompareMemory` at `0x180045828`
- `securekernel!RtlCompareMemory` at `0x18004584b`
- `securekernel!RtlCompareMemory` at `0x1800458ac`
- `securekernel!RtlCompareMemory` at `0x180045828`
- `securekernel!RtlCompareMemory` at `0x18004584b`
- `securekernel!RtlCompareMemory` at `0x1800458ac`

## pseudocode

```c
_BOOL8 __fastcall I_ValidatePageHashesBlob(
        __int64 a1,
        unsigned __int64 a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int *a5)
{
  bool v5; // zf
  __int64 v7; // rbp
  const void *v10; // rdx
  unsigned __int64 v11; // rcx
  __int64 v12; // rdx
  unsigned int *v13; // rbx
  const void *v14; // rdx
  _BOOL8 result; // rax
  int Source1; // [rsp+50h] [rbp+8h] BYREF

  v5 = *(_DWORD *)(a1 + 32) == 10;
  v7 = a4;
  Source1 = 0;
  result = 0;
  if ( v5 )
  {
    v10 = *(const void **)(a1 + 40);
    if ( v10 )
    {
      if ( *(_QWORD *)(a1 + 56)
        && (RtlCompareMemory(qword_180037628, v10, 0xAu) == 10
         || RtlCompareMemory(qword_1800375C0, *(const void **)(a1 + 40), 0xAu) == 10) )
      {
        v11 = *(_QWORD *)(a1 + 56);
        if ( v11 >= a2 )
        {
          v12 = *(unsigned int *)(a1 + 48);
          if ( (unsigned int)v12 <= a3 )
          {
            v13 = a5;
            if ( (int)MinAsn1ExtractContent(v11, v12, a5, a5 + 2) >= 0 && !(*v13 % (unsigned __int64)(v7 + 4)) )
            {
              if ( *v13 / (unsigned __int64)(v7 + 4) )
              {
                v14 = (const void *)*((_QWORD *)v13 + 1);
                if ( v14 )
                {
                  if ( RtlCompareMemory(&Source1, v14, 4u) == 4 )
                    return 1;
                }
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800457dc  push    rbx
0x1800457de  push    rbp
0x1800457df  push    rsi
0x1800457e0  push    rdi
0x1800457e1  sub     rsp, 28h
0x1800457e5  cmp     dword ptr [rcx+20h], 0Ah
0x1800457e9  mov     edi, r8d
0x1800457ec  mov     ebp, r9d
0x1800457ef  mov     rsi, rdx
0x1800457f2  mov     rbx, rcx
0x1800457f5  mov     [rsp+48h+Source1], 0
0x1800457fd  jnz     loc_1800458C5
0x180045803  mov     rdx, [rcx+28h]; Source2
0x180045807  test    rdx, rdx
0x18004580a  jz      loc_1800458C5
0x180045810  cmp     qword ptr [rcx+38h], 0
0x180045815  jz      loc_1800458C5
0x18004581b  mov     r8d, 0Ah; Length
0x180045821  lea     rcx, qword_180037628; Source1
0x180045828  call    cs:__imp_RtlCompareMemory
0x18004582f  nop     dword ptr [rax+rax+00h]
0x180045834  cmp     rax, 0Ah
0x180045838  jz      short loc_18004585D
0x18004583a  mov     rdx, [rbx+28h]; Source2
0x18004583e  lea     rcx, qword_1800375C0; Source1
0x180045845  mov     r8d, 0Ah; Length
0x18004584b  call    cs:__imp_RtlCompareMemory
0x180045852  nop     dword ptr [rax+rax+00h]
0x180045857  cmp     rax, 0Ah
0x18004585b  jnz     short loc_1800458C5
0x18004585d  mov     rcx, [rbx+38h]
0x180045861  cmp     rcx, rsi
0x180045864  jb      short loc_1800458C5
0x180045866  mov     edx, [rbx+30h]
0x180045869  cmp     edx, edi
0x18004586b  ja      short loc_1800458C5
0x18004586d  mov     rbx, [rsp+48h+arg_20]
0x180045872  mov     r8, rbx
0x180045875  lea     r9, [rbx+8]
0x180045879  call    MinAsn1ExtractContent
0x18004587e  test    eax, eax
0x180045880  js      short loc_1800458C5
0x180045882  mov     eax, [rbx]
0x180045884  lea     rcx, [rbp+4]
0x180045888  xor     edx, edx
0x18004588a  div     rcx
0x18004588d  test    rdx, rdx
0x180045890  jnz     short loc_1800458C5
0x180045892  cmp     rax, 1
0x180045896  jb      short loc_1800458C5
0x180045898  mov     rdx, [rbx+8]; Source2
0x18004589c  test    rdx, rdx
0x18004589f  jz      short loc_1800458C5
0x1800458a1  mov     r8d, 4; Length
0x1800458a7  lea     rcx, [rsp+48h+Source1]; Source1
0x1800458ac  call    cs:__imp_RtlCompareMemory
0x1800458b3  nop     dword ptr [rax+rax+00h]
0x1800458b8  cmp     rax, 4
0x1800458bc  jnz     short loc_1800458C5
0x1800458be  mov     eax, 1
0x1800458c3  jmp     short loc_1800458C7
0x1800458c5  xor     eax, eax
0x1800458c7  add     rsp, 28h
0x1800458cb  pop     rdi
0x1800458cc  pop     rsi
0x1800458cd  pop     rbp
0x1800458ce  pop     rbx
0x1800458cf  retn
```
