# GetKeyValue(ushort *,ushort *,ushort,ushort *,void *)

- ea: `0x1800042a0`
- end: `0x180004497`
- name: `?GetKeyValue@@YAGPEAG0G0PEAX@Z`
- size: `503`
- prototype: `unsigned __int16 __usercall@<ax>(wchar_t *Str@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16@<r8w>, unsigned __int16 *@<r9>, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003390`

## callees

- `0x1800042a0`
- `0x180005600`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800043a5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800043db`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800043a5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800043db`
- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x180004431`
- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x180004431`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180004446`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180004446`

## pseudocode

```c
__int64 __fastcall GetKeyValue(wchar_t *Str, unsigned __int16 *a2, __int64 a3, unsigned __int16 *a4, unsigned int *a5)
{
  wchar_t *v7; // rbx
  wchar_t *v9; // r12
  const wchar_t *v10; // r15
  __int16 v11; // cx
  wchar_t v12; // ax
  __int64 v13; // r8
  __int64 v14; // r8
  wchar_t *v15; // rax

  v7 = Str;
  if ( !Str || !a2 )
  {
    if ( a4 )
      goto LABEL_44;
    return 87;
  }
  if ( !a4 )
    return 87;
  if ( !a5 )
  {
LABEL_44:
    *a4 = 0;
    return 87;
  }
  if ( *a4 >= 4u )
  {
    v9 = 0;
    v10 = 0;
LABEL_8:
    v11 = 1;
    while ( v7 )
    {
      v12 = *v7;
      if ( !*v7 )
        break;
      switch ( v12 )
      {
        case 0x3Bu:
          if ( v11 == 16 )
          {
            if ( (unsigned int)_o_iswdigit(*v10, 16, 32) )
            {
              *a5 = wcstoul(v10, 0, 10);
              return 0;
            }
LABEL_31:
            v15 = wcschr(v7, 0x3Bu);
            v7 = v15 + 1;
            if ( !v15 )
              v7 = 0;
            goto LABEL_8;
          }
          v11 = 1;
          ++v7;
          break;
        case 9u:
        case 0x20u:
          if ( v11 == 4 )
          {
            v14 = -1;
            do
              ++v14;
            while ( a2[v14] );
            if ( (unsigned int)_o__wcsnicmp(v9, a2, v14) )
              goto LABEL_31;
            v11 = 8;
          }
          else if ( v11 == 16 )
          {
            v11 = 32;
          }
          ++v7;
          break;
        case 0x3Du:
          if ( v11 != 4 )
            goto LABEL_31;
          v13 = -1;
          do
            ++v13;
          while ( a2[v13] );
          if ( (unsigned int)_o__wcsnicmp(v9, a2, v13) )
            goto LABEL_31;
          ++v7;
          v11 = 2;
          break;
        default:
          switch ( v11 )
          {
            case 8:
            case 32:
              goto LABEL_31;
            case 1:
              v9 = v7;
              v11 = 4;
              break;
            case 2:
              v10 = v7;
              v11 = 16;
              break;
          }
          ++v7;
          break;
      }
    }
    *a4 = 0;
    return 232;
  }
  else
  {
    *a4 = 0;
    return 122;
  }
}

```

## disassembly

```asm
0x1800042a0  push    rbx
0x1800042a2  push    rbp
0x1800042a3  push    rsi
0x1800042a4  push    rdi
0x1800042a5  push    r14
0x1800042a7  sub     rsp, 20h
0x1800042ab  mov     rdi, r9
0x1800042ae  mov     rbp, rdx
0x1800042b1  mov     rbx, rcx
0x1800042b4  test    rcx, rcx
0x1800042b7  jz      loc_180004484
0x1800042bd  test    rdx, rdx
0x1800042c0  jz      loc_180004484
0x1800042c6  test    r9, r9
0x1800042c9  jz      loc_180004490
0x1800042cf  mov     rsi, [rsp+48h+arg_20]
0x1800042d4  test    rsi, rsi
0x1800042d7  jz      loc_180004489
0x1800042dd  xor     r14d, r14d
0x1800042e0  cmp     word ptr [r9], 4
0x1800042e5  jnb     short loc_1800042F5
0x1800042e7  mov     [r9], r14w
0x1800042eb  mov     eax, 7Ah ; 'z'
0x1800042f0  jmp     loc_180004461
0x1800042f5  mov     [rsp+48h+arg_0], r12
0x1800042fa  mov     r12, r14
0x1800042fd  mov     [rsp+48h+arg_8], r13
0x180004302  mov     r13d, 1
0x180004308  mov     [rsp+48h+arg_10], r15
0x18000430d  mov     r15, r14
0x180004310  movzx   ecx, r13w
0x180004314  mov     r8d, 20h ; ' '
0x18000431a  mov     edx, 10h
0x18000431f  nop
0x180004320  test    rbx, rbx
0x180004323  jz      loc_180004479
0x180004329  movzx   eax, word ptr [rbx]
0x18000432c  test    ax, ax
0x18000432f  jz      loc_180004479
0x180004335  cmp     ax, 3Bh ; ';'
0x180004339  jz      loc_180004427
0x18000433f  cmp     ax, 9
0x180004343  jz      short loc_1800043BD
0x180004345  cmp     ax, 20h ; ' '
0x180004349  jz      short loc_1800043BD
0x18000434b  cmp     ax, 3Dh ; '='
0x18000434f  jz      short loc_180004387
0x180004351  cmp     cx, 8
0x180004355  jz      loc_1800043E5
0x18000435b  cmp     cx, 20h ; ' '
0x18000435f  jz      loc_1800043E5
0x180004365  cmp     cx, r13w
0x180004369  jnz     short loc_180004375
0x18000436b  mov     r12, rbx
0x18000436e  mov     ecx, 4
0x180004373  jmp     short loc_180004381
0x180004375  cmp     cx, 2
0x180004379  jnz     short loc_180004381
0x18000437b  mov     r15, rbx
0x18000437e  movzx   ecx, dx
0x180004381  add     rbx, 2
0x180004385  jmp     short loc_180004320
0x180004387  cmp     cx, 4
0x18000438b  jnz     short loc_1800043E5
0x18000438d  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180004394  inc     r8
0x180004397  cmp     [rbp+r8*2+0], r14w
0x18000439d  jnz     short loc_180004394
0x18000439f  mov     rdx, rbp
0x1800043a2  mov     rcx, r12
0x1800043a5  call    cs:__imp__o__wcsnicmp
0x1800043ab  test    eax, eax
0x1800043ad  jnz     short loc_1800043E5
0x1800043af  add     rbx, 2
0x1800043b3  mov     ecx, 2
0x1800043b8  jmp     loc_180004314
0x1800043bd  cmp     cx, 4
0x1800043c1  jnz     short loc_180004414
0x1800043c3  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1800043ca  inc     r8
0x1800043cd  cmp     [rbp+r8*2+0], r14w
0x1800043d3  jnz     short loc_1800043CA
0x1800043d5  mov     rdx, rbp
0x1800043d8  mov     rcx, r12
0x1800043db  call    cs:__imp__o__wcsnicmp
0x1800043e1  test    eax, eax
0x1800043e3  jz      short loc_180004402
0x1800043e5  mov     edx, 3Bh ; ';'; Ch
0x1800043ea  mov     rcx, rbx; Str
0x1800043ed  call    ?wcschr@@YAPEAGPEAGG@Z; wcschr(ushort *,ushort)
0x1800043f2  test    rax, rax
0x1800043f5  lea     rbx, [rax+2]
0x1800043f9  cmovz   rbx, rax
0x1800043fd  jmp     loc_180004310
0x180004402  mov     ecx, 8
0x180004407  mov     edx, 10h
0x18000440c  mov     r8d, 20h ; ' '
0x180004412  jmp     short loc_18000441E
0x180004414  cmp     cx, 10h
0x180004418  jnz     short loc_18000441E
0x18000441a  movzx   ecx, r8w
0x18000441e  add     rbx, 2
0x180004422  jmp     loc_180004320
0x180004427  cmp     cx, 10h
0x18000442b  jnz     short loc_18000446C
0x18000442d  movzx   ecx, word ptr [r15]
0x180004431  call    cs:__imp__o_iswdigit
0x180004437  test    eax, eax
0x180004439  jz      short loc_1800043E5
0x18000443b  xor     edx, edx; EndPtr
0x18000443d  mov     r8d, 0Ah; Radix
0x180004443  mov     rcx, r15; String
0x180004446  call    cs:__imp_wcstoul
0x18000444c  mov     [rsi], eax
0x18000444e  movzx   eax, r14w
0x180004452  mov     r13, [rsp+48h+arg_8]
0x180004457  mov     r12, [rsp+48h+arg_0]
0x18000445c  mov     r15, [rsp+48h+arg_10]
0x180004461  add     rsp, 20h
0x180004465  pop     r14
0x180004467  pop     rdi
0x180004468  pop     rsi
0x180004469  pop     rbp
0x18000446a  pop     rbx
0x18000446b  retn
0x18000446c  movzx   ecx, r13w
0x180004470  add     rbx, 2
0x180004474  jmp     loc_180004320
0x180004479  mov     [rdi], r14w
0x18000447d  mov     eax, 0E8h
0x180004482  jmp     short loc_180004452
0x180004484  test    rdi, rdi
0x180004487  jz      short loc_180004490
0x180004489  xor     r14d, r14d
0x18000448c  mov     [r9], r14w
0x180004490  mov     eax, 57h ; 'W'
0x180004495  jmp     short loc_180004461
```
