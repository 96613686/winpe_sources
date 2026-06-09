# ownGetCacheSize

- ea: `0x18001f793`
- end: `0x18001f840`
- name: `ownGetCacheSize`
- size: `173`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001f793`

## pseudocode

```c
__int64 __fastcall ownGetCacheSize(int *a1)
{
  int *v2; // rbp
  unsigned int v3; // esi
  __int64 result; // rax
  int v10; // edx
  __int64 v11; // rcx
  int v12; // [rsp+0h] [rbp-38h] BYREF
  int v13; // [rsp+4h] [rbp-34h] BYREF

  v2 = &v12;
  v3 = 0;
  _RAX = 2;
  __asm { cpuid }
  if ( (_BYTE)_RAX != 1 )
    return 0xFFFFFFFFLL;
  if ( (int)_RAX < 0 )
    LODWORD(_RAX) = 0;
  if ( (int)_RBX < 0 )
    LODWORD(_RBX) = 0;
  if ( (int)_RCX < 0 )
    LODWORD(_RCX) = 0;
  if ( (int)_RDX < 0 )
    LODWORD(_RDX) = 0;
  if ( (_DWORD)_RAX )
  {
    v12 = _RAX;
    v2 = &v13;
    v3 = 3;
  }
  if ( (_DWORD)_RBX )
  {
    *v2++ = _RBX;
    v3 += 4;
  }
  if ( (_DWORD)_RCX )
  {
    *v2++ = _RCX;
    v3 += 4;
  }
  if ( (_DWORD)_RDX )
  {
    *v2 = _RDX;
    v3 += 4;
  }
  if ( !v3 )
    return 0xFFFFFFFFLL;
  result = 0xFFFFFFFFLL;
LABEL_20:
  v10 = *a1;
  if ( *a1 )
  {
    a1 += 2;
    v11 = v3;
    while ( (_BYTE)v10 != *((_BYTE *)&v12 + v11) )
    {
      v11 = (unsigned int)(v11 - 1);
      if ( !(_DWORD)v11 )
        goto LABEL_20;
    }
    return (unsigned int)*(a1 - 1);
  }
  return result;
}

```

## disassembly

```asm
0x18001f793  push    rsi
0x18001f794  push    rdi
0x18001f795  push    rbx
0x18001f796  push    rbp
0x18001f797  sub     rsp, 18h
0x18001f79b  mov     rdi, rcx
0x18001f79e  mov     rbp, rsp
0x18001f7a1  xor     esi, esi
0x18001f7a3  mov     eax, 2
0x18001f7a8  cpuid
0x18001f7aa  cmp     al, 1
0x18001f7ac  jnz     loc_18001F839
0x18001f7b2  test    eax, 80000000h
0x18001f7b7  jz      short loc_18001F7BB
0x18001f7b9  xor     eax, eax
0x18001f7bb  test    ebx, 80000000h
0x18001f7c1  jz      short loc_18001F7C5
0x18001f7c3  xor     ebx, ebx
0x18001f7c5  test    ecx, 80000000h
0x18001f7cb  jz      short loc_18001F7CF
0x18001f7cd  xor     ecx, ecx
0x18001f7cf  test    edx, 80000000h
0x18001f7d5  jz      short loc_18001F7D9
0x18001f7d7  xor     edx, edx
0x18001f7d9  test    eax, eax
0x18001f7db  jz      short loc_18001F7E7
0x18001f7dd  mov     [rbp+0], eax
0x18001f7e0  add     rbp, 4
0x18001f7e4  add     esi, 3
0x18001f7e7  test    ebx, ebx
0x18001f7e9  jz      short loc_18001F7F5
0x18001f7eb  mov     [rbp+0], ebx
0x18001f7ee  add     rbp, 4
0x18001f7f2  add     esi, 4
0x18001f7f5  test    ecx, ecx
0x18001f7f7  jz      short loc_18001F803
0x18001f7f9  mov     [rbp+0], ecx
0x18001f7fc  add     rbp, 4
0x18001f800  add     esi, 4
0x18001f803  test    edx, edx
0x18001f805  jz      short loc_18001F80D
0x18001f807  mov     [rbp+0], edx
0x18001f80a  add     esi, 4
0x18001f80d  test    esi, esi
0x18001f80f  jz      short loc_18001F839
0x18001f811  mov     eax, 0FFFFFFFFh
0x18001f816  xor     edx, edx
0x18001f818  add     edx, [rdi]
0x18001f81a  jz      short loc_18001F830
0x18001f81c  add     rdi, 8
0x18001f820  mov     ecx, esi
0x18001f822  cmp     dl, [rsp+rcx+38h+var_38]
0x18001f825  jz      short loc_18001F82D
0x18001f827  dec     ecx
0x18001f829  jnz     short loc_18001F822
0x18001f82b  jmp     short loc_18001F816
0x18001f82d  mov     eax, [rdi-4]
0x18001f830  add     rsp, 18h
0x18001f834  pop     rbp
0x18001f835  pop     rbx
0x18001f836  pop     rdi
0x18001f837  pop     rsi
0x18001f838  retn
0x18001f839  mov     eax, 0FFFFFFFFh
0x18001f83e  jmp     short loc_18001F830
```
