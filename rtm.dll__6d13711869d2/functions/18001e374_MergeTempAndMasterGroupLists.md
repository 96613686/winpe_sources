# MergeTempAndMasterGroupLists

- ea: `0x18001e374`
- end: `0x18001e4a9`
- name: `MergeTempAndMasterGroupLists`
- size: `309`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180019de0`
- `0x18001a360`
- `0x18001ca9c`
- `0x18001ed64`

## callees

- `0x180014d2c`
- `0x180015178`
- `0x18001e374`

## pseudocode

```c
void __fastcall MergeTempAndMasterGroupLists(__int64 *a1)
{
  __int64 i; // r8
  __int64 v3; // rcx
  __int64 v4; // rax
  __int64 *v5; // rax
  unsigned int v6; // r10d
  unsigned int v7; // r9d
  int v8; // edx
  __int64 *v9; // rax

  AcquireWriteLock(&qword_18002BA30);
  if ( (__int64 *)*a1 != a1 )
  {
LABEL_2:
    for ( i = qword_18002BA20; ; *(_QWORD *)(i + 8) = v3 )
    {
      v3 = *a1;
      if ( (__int64 *)*a1 == a1 )
        break;
      if ( *(__int64 **)(v3 + 8) != a1 )
        goto LABEL_19;
      v4 = *(_QWORD *)v3;
      if ( *(_QWORD *)(*(_QWORD *)v3 + 8LL) != v3 )
        goto LABEL_19;
      *a1 = v4;
      *(_QWORD *)(v4 + 8) = a1;
      if ( (__int64 *)qword_18002BA20 == &qword_18002BA20 )
      {
        v5 = (__int64 *)qword_18002BA28;
        if ( *(__int64 **)qword_18002BA28 != &qword_18002BA20 )
LABEL_19:
          __fastfail(3u);
        *(_QWORD *)v3 = &qword_18002BA20;
        *(_QWORD *)(v3 + 8) = v5;
        *v5 = v3;
        qword_18002BA28 = v3;
        goto LABEL_2;
      }
      if ( (__int64 *)i != &qword_18002BA20 )
      {
        v6 = *(_DWORD *)(v3 + 32);
        do
        {
          v7 = *(_DWORD *)(i + 32);
          v8 = (unsigned __int8)v6 - (unsigned __int8)v7;
          if ( (unsigned __int8)v6 == (unsigned __int8)v7 )
          {
            v8 = (*(_DWORD *)(v3 + 32) & 0xFF00) - (*(_DWORD *)(i + 32) & 0xFF00);
            if ( !v8 )
            {
              v8 = (v6 & 0xFF0000) - (v7 & 0xFF0000);
              if ( (v6 & 0xFF0000) == (v7 & 0xFF0000) )
                v8 = ((v6 >> 8) & 0xFF0000) - ((v7 >> 8) & 0xFF0000);
            }
          }
          if ( v8 < 0 )
            break;
          i = *(_QWORD *)i;
        }
        while ( (__int64 *)i != &qword_18002BA20 );
      }
      v9 = *(__int64 **)(i + 8);
      if ( *v9 != i )
        goto LABEL_19;
      *(_QWORD *)v3 = i;
      *(_QWORD *)(v3 + 8) = v9;
      *v9 = v3;
    }
    dword_18002B9F8 = 0;
  }
  ReleaseWriteLock((__int64)&qword_18002BA30);
}

```

## disassembly

```asm
0x18001e374  mov     [rsp+arg_0], rbx
0x18001e379  mov     [rsp+arg_8], rsi
0x18001e37e  push    rdi
0x18001e37f  sub     rsp, 20h
0x18001e383  mov     rbx, rcx
0x18001e386  lea     rcx, qword_18002BA30
0x18001e38d  call    AcquireWriteLock
0x18001e392  cmp     [rbx], rbx
0x18001e395  jz      loc_18001E48E
0x18001e39b  lea     rdi, qword_18002BA20
0x18001e3a2  mov     esi, 0FF0000h
0x18001e3a7  mov     r8, cs:qword_18002BA20
0x18001e3ae  mov     rcx, [rbx]
0x18001e3b1  cmp     rcx, rbx
0x18001e3b4  jz      loc_18001E484
0x18001e3ba  cmp     [rcx+8], rbx
0x18001e3be  jnz     loc_18001E47D
0x18001e3c4  mov     rax, [rcx]
0x18001e3c7  cmp     [rax+8], rcx
0x18001e3cb  jnz     loc_18001E47D
0x18001e3d1  mov     [rbx], rax
0x18001e3d4  mov     [rax+8], rbx
0x18001e3d8  cmp     cs:qword_18002BA20, rdi
0x18001e3df  jnz     short loc_18001E404
0x18001e3e1  mov     rax, cs:qword_18002BA28
0x18001e3e8  cmp     [rax], rdi
0x18001e3eb  jnz     loc_18001E47D
0x18001e3f1  mov     [rcx], rdi
0x18001e3f4  mov     [rcx+8], rax
0x18001e3f8  mov     [rax], rcx
0x18001e3fb  mov     cs:qword_18002BA28, rcx
0x18001e402  jmp     short loc_18001E3A7
0x18001e404  cmp     r8, rdi
0x18001e407  jz      short loc_18001E461
0x18001e409  mov     r10d, [rcx+20h]
0x18001e40d  movzx   r11d, r10b
0x18001e411  mov     r9d, [r8+20h]
0x18001e415  mov     edx, r11d
0x18001e418  movzx   eax, r9b
0x18001e41c  sub     edx, eax
0x18001e41e  jnz     short loc_18001E455
0x18001e420  mov     eax, r9d
0x18001e423  mov     edx, r10d
0x18001e426  and     eax, 0FF00h
0x18001e42b  and     edx, 0FF00h
0x18001e431  sub     edx, eax
0x18001e433  jnz     short loc_18001E455
0x18001e435  mov     eax, r9d
0x18001e438  mov     edx, r10d
0x18001e43b  and     eax, esi
0x18001e43d  and     edx, esi
0x18001e43f  sub     edx, eax
0x18001e441  jnz     short loc_18001E455
0x18001e443  shr     r9d, 8
0x18001e447  mov     edx, r10d
0x18001e44a  shr     edx, 8
0x18001e44d  and     r9d, esi
0x18001e450  and     edx, esi
0x18001e452  sub     edx, r9d
0x18001e455  test    edx, edx
0x18001e457  js      short loc_18001E461
0x18001e459  mov     r8, [r8]
0x18001e45c  cmp     r8, rdi
0x18001e45f  jnz     short loc_18001E411
0x18001e461  mov     rax, [r8+8]
0x18001e465  cmp     [rax], r8
0x18001e468  jnz     short loc_18001E47D
0x18001e46a  mov     [rcx], r8
0x18001e46d  mov     [rcx+8], rax
0x18001e471  mov     [rax], rcx
0x18001e474  mov     [r8+8], rcx
0x18001e478  jmp     loc_18001E3AE
0x18001e47d  mov     ecx, 3
0x18001e482  int     29h; Win8: RtlFailFast(ecx)
0x18001e484  mov     cs:dword_18002B9F8, 0
0x18001e48e  lea     rcx, qword_18002BA30
0x18001e495  mov     rbx, [rsp+28h+arg_0]
0x18001e49a  mov     rsi, [rsp+28h+arg_8]
0x18001e49f  add     rsp, 20h
0x18001e4a3  pop     rdi
0x18001e4a4  jmp     ReleaseWriteLock
```
