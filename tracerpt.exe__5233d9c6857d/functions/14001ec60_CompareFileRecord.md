# CompareFileRecord

- ea: `0x14001ec60`
- end: `0x14001eca6`
- name: `CompareFileRecord`
- size: `70`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14001ec60`

## pseudocode

```c
__int64 __fastcall CompareFileRecord(_DWORD *a1, _DWORD *a2)
{
  __int64 result; // rax
  __int64 v3; // rcx
  __int64 v4; // rdx
  unsigned __int16 *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rdx
  unsigned __int16 v8; // ax

  result = (unsigned int)(a2[2] - a1[2]);
  if ( !(_DWORD)result )
  {
    v3 = *(_QWORD *)a1;
    v4 = *(_QWORD *)a2;
    result = (unsigned int)(*(_DWORD *)(v3 + 48) - *(_DWORD *)(v4 + 48));
    if ( !(_DWORD)result )
    {
      v5 = *(unsigned __int16 **)(v3 + 40);
      if ( v5 )
      {
        v6 = *(_QWORD *)(v4 + 40);
        if ( v6 )
        {
          v7 = v6 - (_QWORD)v5;
          while ( 1 )
          {
            v8 = *v5;
            if ( *v5 != *(unsigned __int16 *)((char *)v5 + v7) )
              break;
            ++v5;
            if ( !v8 )
              return 0;
          }
          return v8 < *(unsigned __int16 *)((char *)v5 + v7) ? -1 : 1;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001ec60  mov     eax, [rdx+8]
0x14001ec63  sub     eax, [rcx+8]
0x14001ec66  jnz     short locret_14001ECA5
0x14001ec68  mov     rcx, [rcx]
0x14001ec6b  mov     rdx, [rdx]
0x14001ec6e  mov     eax, [rcx+30h]
0x14001ec71  sub     eax, [rdx+30h]
0x14001ec74  jnz     short locret_14001ECA5
0x14001ec76  mov     rcx, [rcx+28h]
0x14001ec7a  test    rcx, rcx
0x14001ec7d  jz      short locret_14001ECA5
0x14001ec7f  mov     rdx, [rdx+28h]
0x14001ec83  test    rdx, rdx
0x14001ec86  jz      short locret_14001ECA5
0x14001ec88  sub     rdx, rcx
0x14001ec8b  movzx   eax, word ptr [rcx]
0x14001ec8e  cmp     ax, [rcx+rdx]
0x14001ec92  jnz     short loc_14001ECA0
0x14001ec94  add     rcx, 2
0x14001ec98  test    ax, ax
0x14001ec9b  jnz     short loc_14001EC8B
0x14001ec9d  xor     eax, eax
0x14001ec9f  retn
0x14001eca0  sbb     eax, eax
0x14001eca2  or      eax, 1
0x14001eca5  retn
```
