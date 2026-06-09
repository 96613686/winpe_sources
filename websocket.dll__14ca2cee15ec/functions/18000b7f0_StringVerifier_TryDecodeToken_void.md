# StringVerifier::TryDecodeToken(void)

- ea: `0x18000b7f0`
- end: `0x18000b884`
- name: `?TryDecodeToken@StringVerifier@@AEAAHXZ`
- size: `148`
- prototype: `__int64 __fastcall(StringVerifier *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b620`

## callees

- `0x18000b7f0`

## pseudocode

```c
__int64 __fastcall StringVerifier::TryDecodeToken(StringVerifier *this)
{
  _BYTE *v1; // rdx
  __int64 v2; // r9
  __int64 v3; // r8
  unsigned __int8 v4; // al
  char *v5; // rax
  unsigned __int64 v6; // rdx
  __int64 v7; // r8
  unsigned __int8 v8; // dl

  v1 = (_BYTE *)*((_QWORD *)this + 1);
  if ( (unsigned __int64)v1 >= *((_QWORD *)this + 2) )
    return 0;
  v2 = 0x2BFFFFFFE3FFFFFFLL;
  if ( *v1 > 0x39u || (v3 = 0x3FF6CFB00000000LL, !_bittest64(&v3, (char)*v1)) )
  {
    v4 = *v1 - 65;
    if ( v4 > 0x3Du || !_bittest64(&v2, (char)v4) )
      return 0;
  }
  if ( *v1 == 32 )
    return 0;
  v5 = v1 + 1;
  for ( *((_QWORD *)this + 1) = v1 + 1; (unsigned __int64)v5 < *((_QWORD *)this + 2); v5 = (char *)*((_QWORD *)this + 1) )
  {
    v6 = *v5;
    if ( (unsigned __int8)v6 > 0x39u || (v7 = 0x3FF6CFA00000000LL, !_bittest64(&v7, v6)) )
    {
      v8 = v6 - 65;
      if ( v8 > 0x3Du || !_bittest64(&v2, (char)v8) )
        break;
    }
    ++*((_QWORD *)this + 1);
  }
  return 1;
}

```

## disassembly

```asm
0x18000b7f0  mov     rdx, [rcx+8]
0x18000b7f4  cmp     rdx, [rcx+10h]
0x18000b7f8  jnb     loc_18000B881
0x18000b7fe  cmp     byte ptr [rdx], 39h ; '9'
0x18000b801  mov     r9, 2BFFFFFFE3FFFFFFh
0x18000b80b  ja      short loc_18000B821
0x18000b80d  movsx   rax, byte ptr [rdx]
0x18000b811  mov     r8, 3FF6CFB00000000h
0x18000b81b  bt      r8, rax
0x18000b81f  jb      short loc_18000B833
0x18000b821  mov     al, [rdx]
0x18000b823  sub     al, 41h ; 'A'
0x18000b825  cmp     al, 3Dh ; '='
0x18000b827  ja      short loc_18000B881
0x18000b829  movsx   rax, al
0x18000b82d  bt      r9, rax
0x18000b831  jnb     short loc_18000B881
0x18000b833  cmp     byte ptr [rdx], 20h ; ' '
0x18000b836  jz      short loc_18000B881
0x18000b838  lea     rax, [rdx+1]
0x18000b83c  mov     [rcx+8], rax
0x18000b840  jmp     short loc_18000B875
0x18000b842  movsx   rdx, byte ptr [rax]
0x18000b846  cmp     dl, 39h ; '9'
0x18000b849  ja      short loc_18000B85B
0x18000b84b  mov     r8, 3FF6CFA00000000h
0x18000b855  bt      r8, rdx
0x18000b859  jb      short loc_18000B86D
0x18000b85b  sub     dl, 41h ; 'A'
0x18000b85e  cmp     dl, 3Dh ; '='
0x18000b861  ja      short loc_18000B87B
0x18000b863  movsx   rax, dl
0x18000b867  bt      r9, rax
0x18000b86b  jnb     short loc_18000B87B
0x18000b86d  inc     qword ptr [rcx+8]
0x18000b871  mov     rax, [rcx+8]
0x18000b875  cmp     rax, [rcx+10h]
0x18000b879  jb      short loc_18000B842
0x18000b87b  mov     eax, 1
0x18000b880  retn
0x18000b881  xor     eax, eax
0x18000b883  retn
```
