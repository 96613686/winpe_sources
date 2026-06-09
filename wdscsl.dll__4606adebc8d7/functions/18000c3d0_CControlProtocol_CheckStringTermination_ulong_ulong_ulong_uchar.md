# CControlProtocol::CheckStringTermination(ulong,ulong,ulong,uchar *)

- ea: `0x18000c3d0`
- end: `0x18000c4f1`
- name: `?CheckStringTermination@CControlProtocol@@AEAAHKKKPEAE@Z`
- size: `289`
- prototype: `_BOOL8 __fastcall(CControlProtocol *this, int, unsigned int, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000c8bc`

## callees

- `0x18000c3d0`

## pseudocode

```c
_BOOL8 __fastcall CControlProtocol::CheckStringTermination(
        CControlProtocol *this,
        int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int8 *a5)
{
  unsigned __int64 v5; // rbx
  char v6; // r10
  int v7; // r11d
  unsigned __int8 *v8; // r8
  unsigned __int64 j; // rax
  signed int v10; // eax
  unsigned __int8 *v12; // rdx
  unsigned __int64 i; // rax
  signed int v14; // eax

  v5 = a3;
  v6 = a2;
  if ( (a2 & 0x10000000) == 0 )
  {
    v12 = a5;
    i = a3;
    if ( (v6 & 0x20) != 0 )
    {
      if ( a5 )
      {
        for ( i = (unsigned __int64)a3 >> 1; i; --i )
        {
          if ( !*(_WORD *)v12 )
            break;
          v12 += 2;
        }
LABEL_32:
        v14 = i == 0 ? 0x80070057 : 0;
        return v14 >= 0;
      }
    }
    else if ( a5 && a3 <= 0x7FFFFFFFuLL )
    {
      if ( a3 )
      {
        do
        {
          if ( !*v12 )
            break;
          ++v12;
          --i;
        }
        while ( i );
      }
      goto LABEL_32;
    }
    v14 = -2147024809;
    return v14 >= 0;
  }
  if ( a4 )
  {
    v7 = 0;
    while ( 1 )
    {
      v8 = &a5[(unsigned int)(v5 * v7)];
      if ( (a2 & 0x20) != 0 )
      {
        if ( !v8 )
          goto LABEL_16;
        for ( j = v5 >> 1; j; --j )
        {
          if ( !*(_WORD *)v8 )
            break;
          v8 += 2;
        }
      }
      else
      {
        if ( !v8 || v5 > 0x7FFFFFFF )
        {
LABEL_16:
          v10 = -2147024809;
          goto LABEL_17;
        }
        j = v5;
        if ( (_DWORD)v5 )
        {
          do
          {
            if ( !*v8 )
              break;
            ++v8;
            --j;
          }
          while ( j );
        }
      }
      v10 = j == 0 ? 0x80070057 : 0;
LABEL_17:
      if ( v10 < 0 )
        return 0;
      if ( ++v7 >= a4 )
        return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000c3d0  mov     [rsp+arg_0], rbx
0x18000c3d5  mov     [rsp+arg_8], rsi
0x18000c3da  mov     [rsp+arg_10], rdi
0x18000c3df  xor     ecx, ecx
0x18000c3e1  mov     ebx, r8d
0x18000c3e4  mov     r10d, edx
0x18000c3e7  bt      edx, 1Ch
0x18000c3eb  jnb     loc_18000C480
0x18000c3f1  test    r9d, r9d
0x18000c3f4  jz      loc_18000C47C
0x18000c3fa  mov     rsi, [rsp+arg_20]
0x18000c3ff  mov     r11d, ecx
0x18000c402  and     r10d, 20h
0x18000c406  mov     edx, 80070057h
0x18000c40b  mov     r8d, r11d
0x18000c40e  imul    r8d, ebx
0x18000c412  add     r8, rsi
0x18000c415  test    r10d, r10d
0x18000c418  jz      short loc_18000C439
0x18000c41a  test    r8, r8
0x18000c41d  jz      short loc_18000C467
0x18000c41f  mov     rax, rbx
0x18000c422  shr     rax, 1
0x18000c425  jz      short loc_18000C45C
0x18000c427  cmp     [r8], cx
0x18000c42b  jz      short loc_18000C45C
0x18000c42d  add     r8, 2
0x18000c431  sub     rax, 1
0x18000c435  jnz     short loc_18000C427
0x18000c437  jmp     short loc_18000C45C
0x18000c439  test    r8, r8
0x18000c43c  jz      short loc_18000C467
0x18000c43e  cmp     rbx, 7FFFFFFFh
0x18000c445  ja      short loc_18000C467
0x18000c447  mov     rax, rbx
0x18000c44a  test    ebx, ebx
0x18000c44c  jz      short loc_18000C45C
0x18000c44e  cmp     [r8], cl
0x18000c451  jz      short loc_18000C45C
0x18000c453  inc     r8
0x18000c456  sub     rax, 1
0x18000c45a  jnz     short loc_18000C44E
0x18000c45c  neg     rax
0x18000c45f  sbb     eax, eax
0x18000c461  not     eax
0x18000c463  and     eax, edx
0x18000c465  jmp     short loc_18000C469
0x18000c467  mov     eax, edx
0x18000c469  test    eax, eax
0x18000c46b  js      short loc_18000C47C
0x18000c46d  inc     r11d
0x18000c470  cmp     r11d, r9d
0x18000c473  jb      short loc_18000C40B
0x18000c475  mov     eax, 1
0x18000c47a  jmp     short loc_18000C4E0
0x18000c47c  xor     eax, eax
0x18000c47e  jmp     short loc_18000C4E0
0x18000c480  mov     rdx, [rsp+arg_20]
0x18000c485  mov     rax, rbx
0x18000c488  test    r10b, 20h
0x18000c48c  jz      short loc_18000C4A9
0x18000c48e  test    rdx, rdx
0x18000c491  jz      short loc_18000C4D6
0x18000c493  shr     rax, 1
0x18000c496  jz      short loc_18000C4C8
0x18000c498  cmp     [rdx], cx
0x18000c49b  jz      short loc_18000C4C8
0x18000c49d  add     rdx, 2
0x18000c4a1  sub     rax, 1
0x18000c4a5  jnz     short loc_18000C498
0x18000c4a7  jmp     short loc_18000C4C8
0x18000c4a9  test    rdx, rdx
0x18000c4ac  jz      short loc_18000C4D6
0x18000c4ae  cmp     rax, 7FFFFFFFh
0x18000c4b4  ja      short loc_18000C4D6
0x18000c4b6  test    r8d, r8d
0x18000c4b9  jz      short loc_18000C4C8
0x18000c4bb  cmp     [rdx], cl
0x18000c4bd  jz      short loc_18000C4C8
0x18000c4bf  inc     rdx
0x18000c4c2  sub     rax, 1
0x18000c4c6  jnz     short loc_18000C4BB
0x18000c4c8  neg     rax
0x18000c4cb  sbb     eax, eax
0x18000c4cd  not     eax
0x18000c4cf  and     eax, 80070057h
0x18000c4d4  jmp     short loc_18000C4DB
0x18000c4d6  mov     eax, 80070057h
0x18000c4db  not     eax
0x18000c4dd  shr     eax, 1Fh
0x18000c4e0  mov     rbx, [rsp+arg_0]
0x18000c4e5  mov     rsi, [rsp+arg_8]
0x18000c4ea  mov     rdi, [rsp+arg_10]
0x18000c4ef  retn
```
