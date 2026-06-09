# FindOutInterfaceEntry

- ea: `0x18001dcbc`
- end: `0x18001dd84`
- name: `FindOutInterfaceEntry`
- size: `200`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180019de0`
- `0x18001a360`
- `0x18001aa4c`
- `0x18001ad04`
- `0x18001af20`
- `0x18001c1a8`
- `0x18001c790`
- `0x18001d378`
- `0x18001d908`
- `0x18001de54`

## callees

- `0x18001dcbc`

## pseudocode

```c
__int64 __fastcall FindOutInterfaceEntry(
        __int64 **a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        _DWORD *a6,
        _QWORD *a7)
{
  unsigned int v7; // ebx
  __int64 *v8; // r10
  unsigned int v11; // edx
  int v12; // ecx

  v7 = 0;
  v8 = *a1;
  *a7 = 0;
  *a6 = 1;
  if ( v8 != (__int64 *)a1 )
  {
    while ( 1 )
    {
      if ( *((_DWORD *)v8 + 6) >= a4 )
      {
        if ( *((_DWORD *)v8 + 6) > a4 )
          goto LABEL_17;
        if ( *((_DWORD *)v8 + 7) >= a5 )
        {
          if ( *((_DWORD *)v8 + 7) > a5 )
            goto LABEL_17;
          *a6 = 0;
          if ( *((_DWORD *)v8 + 4) >= a2 )
          {
            if ( *((_DWORD *)v8 + 4) > a2 )
            {
LABEL_17:
              *a7 = v8;
              return v7;
            }
            v11 = *((_DWORD *)v8 + 5);
            v12 = (unsigned __int8)v11 - (unsigned __int8)a3;
            if ( (unsigned __int8)v11 == (unsigned __int8)a3 )
            {
              v12 = (*((_DWORD *)v8 + 5) & 0xFF00) - (a3 & 0xFF00);
              if ( !v12 )
              {
                v12 = (v11 & 0xFF0000) - (a3 & 0xFF0000);
                if ( (v11 & 0xFF0000) == (a3 & 0xFF0000) )
                  v12 = ((v11 >> 8) & 0xFF0000) - ((a3 >> 8) & 0xFF0000);
              }
            }
            if ( v12 >= 0 )
              break;
          }
        }
      }
      v8 = (__int64 *)*v8;
      if ( v8 == (__int64 *)a1 )
        return v7;
    }
    *a7 = v8;
    if ( v12 <= 0 )
      return 1;
  }
  return v7;
}

```

## disassembly

```asm
0x18001dcbc  push    rbx
0x18001dcbe  push    rbp
0x18001dcbf  push    rsi
0x18001dcc0  push    rdi
0x18001dcc1  push    r12
0x18001dcc3  push    r14
0x18001dcc5  mov     r11, [rsp+30h+arg_30]
0x18001dcca  xor     ebx, ebx
0x18001dccc  mov     r14, [rsp+30h+arg_28]
0x18001dcd1  mov     esi, r9d
0x18001dcd4  mov     r10, [rcx]
0x18001dcd7  mov     ebp, edx
0x18001dcd9  mov     rdi, rcx
0x18001dcdc  mov     [r11], rbx
0x18001dcdf  mov     dword ptr [r14], 1
0x18001dce6  cmp     r10, rcx
0x18001dce9  jz      loc_18001DD79
0x18001dcef  mov     r9d, [rsp+30h+arg_20]
0x18001dcf4  mov     r12d, 0FF0000h
0x18001dcfa  cmp     [r10+18h], esi
0x18001dcfe  jb      short loc_18001DD5E
0x18001dd00  ja      short loc_18001DD76
0x18001dd02  cmp     [r10+1Ch], r9d
0x18001dd06  jb      short loc_18001DD5E
0x18001dd08  ja      short loc_18001DD76
0x18001dd0a  mov     [r14], ebx
0x18001dd0d  cmp     [r10+10h], ebp
0x18001dd11  jb      short loc_18001DD5E
0x18001dd13  ja      short loc_18001DD76
0x18001dd15  mov     edx, [r10+14h]
0x18001dd19  movzx   ecx, dl
0x18001dd1c  movzx   eax, r8b
0x18001dd20  sub     ecx, eax
0x18001dd22  jnz     short loc_18001DD5A
0x18001dd24  mov     eax, r8d
0x18001dd27  mov     ecx, edx
0x18001dd29  and     eax, 0FF00h
0x18001dd2e  and     ecx, 0FF00h
0x18001dd34  sub     ecx, eax
0x18001dd36  jnz     short loc_18001DD5A
0x18001dd38  mov     ecx, edx
0x18001dd3a  mov     eax, r8d
0x18001dd3d  and     ecx, r12d
0x18001dd40  and     eax, r12d
0x18001dd43  sub     ecx, eax
0x18001dd45  jnz     short loc_18001DD5A
0x18001dd47  mov     ecx, edx
0x18001dd49  mov     eax, r8d
0x18001dd4c  shr     ecx, 8
0x18001dd4f  shr     eax, 8
0x18001dd52  and     ecx, r12d
0x18001dd55  and     eax, r12d
0x18001dd58  sub     ecx, eax
0x18001dd5a  test    ecx, ecx
0x18001dd5c  jns     short loc_18001DD68
0x18001dd5e  mov     r10, [r10]
0x18001dd61  cmp     r10, rdi
0x18001dd64  jnz     short loc_18001DCFA
0x18001dd66  jmp     short loc_18001DD79
0x18001dd68  mov     [r11], r10
0x18001dd6b  test    ecx, ecx
0x18001dd6d  jg      short loc_18001DD79
0x18001dd6f  mov     ebx, 1
0x18001dd74  jmp     short loc_18001DD79
0x18001dd76  mov     [r11], r10
0x18001dd79  mov     eax, ebx
0x18001dd7b  pop     r14
0x18001dd7d  pop     r12
0x18001dd7f  pop     rdi
0x18001dd80  pop     rsi
0x18001dd81  pop     rbp
0x18001dd82  pop     rbx
0x18001dd83  retn
```
