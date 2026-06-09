# RtlImageNtHeaderEx

- ea: `0x1400d7280`
- end: `0x1400d7320`
- name: `RtlImageNtHeaderEx`
- size: `160`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `39`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1400280b0`
- `0x14002a0b0`
- `0x1400346b0`
- `0x140037690`
- `0x140046cb0`
- `0x140047dcc`
- `0x14005896c`
- `0x140058d88`
- `0x140059698`
- `0x14005982c`
- `0x140060bd4`
- `0x140062a88`
- `0x14006ec6c`
- `0x14006f118`
- `0x14007a358`
- `0x14007b814`
- `0x14007da7c`
- `0x14007dc68`
- `0x14007f214`
- `0x140081604`
- `0x140082d58`
- `0x14009a474`
- `0x1400a3ef0`
- `0x1400a8db4`
- `0x1400a9978`
- `0x1400ae76c`
- `0x1400b2aa4`
- `0x1400b8ad4`
- `0x1400bbd0c`
- `0x1400d65ac`
- `0x1400d67c0`
- `0x1400d724c`
- `0x1400dba50`
- `0x1400dc4e8`
- `0x1400dcac4`
- `0x1400e3938`
- `0x1400fe3f0`
- `0x1400fe7e0`
- `0x1400fece0`

## callees

- `0x1400d7280`

## pseudocode

```c
__int64 __fastcall RtlImageNtHeaderEx(int a1, unsigned __int64 a2, unsigned __int64 a3, _QWORD *a4)
{
  char v5; // al
  __int64 result; // rax
  unsigned __int64 v7; // r9
  _DWORD *v8; // rcx

  if ( !a4 )
    return 3221225485LL;
  *a4 = 0;
  if ( (a1 & 0xFFFFFFFE) != 0 || a2 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    return 3221225485LL;
  v5 = 1;
  if ( (a1 & 1) != 0 )
  {
    v5 = 0;
  }
  else if ( a3 < 0x40 )
  {
    return 3221225595LL;
  }
  if ( *(_WORD *)a2 != 23117 )
    return 3221225595LL;
  v7 = *(unsigned int *)(a2 + 60);
  if ( v5 )
  {
    if ( v7 >= a3 || (unsigned int)v7 >= 0xFFFFFFE7 || v7 + 24 >= a3 )
      return 3221225595LL;
  }
  v8 = (_DWORD *)(a2 + v7);
  if ( a2 + v7 < a2 || a2 < 0x7FFFFFFF0000LL && (v8 + 66 < v8 || (unsigned __int64)(v8 + 66) > 0x7FFFFFFF0000LL) )
    return 3221225595LL;
  if ( *v8 != 17744 )
    return 3221225595LL;
  result = 0;
  *a4 = v8;
  return result;
}

```

## disassembly

```asm
0x1400d7280  mov     r10, r9
0x1400d7283  test    r9, r9
0x1400d7286  jz      loc_1400D731A
0x1400d728c  mov     qword ptr [r9], 0
0x1400d7293  test    ecx, 0FFFFFFFEh
0x1400d7299  jnz     short loc_1400D731A
0x1400d729b  lea     rax, [rdx-1]
0x1400d729f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400d72a3  ja      short loc_1400D731A
0x1400d72a5  mov     al, 1
0x1400d72a7  test    al, cl
0x1400d72a9  jnz     short loc_1400D72B8
0x1400d72ab  cmp     r8, 40h ; '@'
0x1400d72af  jnb     short loc_1400D72BA
0x1400d72b1  mov     eax, 0C000007Bh
0x1400d72b6  retn
0x1400d72b8  xor     al, al
0x1400d72ba  mov     ecx, 5A4Dh
0x1400d72bf  cmp     [rdx], cx
0x1400d72c2  jnz     short loc_1400D72B1
0x1400d72c4  mov     r9d, [rdx+3Ch]
0x1400d72c8  mov     ecx, r9d
0x1400d72cb  test    al, al
0x1400d72cd  jz      short loc_1400D72E3
0x1400d72cf  cmp     rcx, r8
0x1400d72d2  jnb     short loc_1400D72B1
0x1400d72d4  cmp     r9d, 0FFFFFFE7h
0x1400d72d8  jnb     short loc_1400D72B1
0x1400d72da  lea     rax, [r9+18h]
0x1400d72de  cmp     rax, r8
0x1400d72e1  jnb     short loc_1400D72B1
0x1400d72e3  add     rcx, rdx
0x1400d72e6  cmp     rcx, rdx
0x1400d72e9  jb      short loc_1400D72B1
0x1400d72eb  mov     r8, 7FFFFFFF0000h
0x1400d72f5  cmp     rdx, r8
0x1400d72f8  jnb     short loc_1400D730B
0x1400d72fa  lea     rax, [rcx+108h]
0x1400d7301  cmp     rax, rcx
0x1400d7304  jbe     short loc_1400D72B1
0x1400d7306  cmp     rax, r8
0x1400d7309  ja      short loc_1400D72B1
0x1400d730b  cmp     dword ptr [rcx], 4550h
0x1400d7311  jnz     short loc_1400D72B1
0x1400d7313  xor     eax, eax
0x1400d7315  mov     [r10], rcx
0x1400d7318  retn
0x1400d731a  mov     eax, 0C000000Dh
0x1400d731f  retn
```
