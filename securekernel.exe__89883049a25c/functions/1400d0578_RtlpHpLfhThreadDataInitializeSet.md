# RtlpHpLfhThreadDataInitializeSet

- ea: `0x1400d0578`
- end: `0x1400d05f9`
- name: `RtlpHpLfhThreadDataInitializeSet`
- size: `129`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000f0f0`
- `0x14000ffec`
- `0x140013c44`
- `0x14001c210`
- `0x1400c7b18`
- `0x1400cdf4c`
- `0x1400cf2cc`

## callees

- `0x1400b5904`
- `0x1400d0578`

## pseudocode

```c
__int64 __fastcall RtlpHpLfhThreadDataInitializeSet(__int64 a1)
{
  char CurrentProcessorNumber; // dl
  unsigned int v3; // eax
  unsigned int v4; // edx
  __int64 result; // rax
  __int64 v6; // [rsp+30h] [rbp+8h]

  CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
  v3 = *(unsigned __int8 *)(a1 + 64);
  v4 = CurrentProcessorNumber & 0x3F;
  if ( v4 >= v3 )
  {
    if ( v4 == v3 || (_BYTE)v3 == 1 )
      v4 = 0;
    else
      v4 = *(unsigned __int8 *)(v4 - v3 - 1 + *(_QWORD *)(a1 + 56));
  }
  v6 = (unsigned __int16)((((unsigned __int64)v4 << 8) + 1472) >> 6);
  WORD1(v6) = 3;
  result = v6;
  *((_QWORD *)&KeGetPcr()->NtTib.ExceptionList[182].Handler + (unsigned int)(*(_DWORD *)(a1 + 76) - 1)) = v6;
  return result;
}

```

## disassembly

```asm
0x1400d0578  push    rbx
0x1400d057a  sub     rsp, 20h
0x1400d057e  mov     rbx, rcx
0x1400d0581  xor     ecx, ecx; ProcNumber
0x1400d0583  call    KeGetCurrentProcessorNumberEx
0x1400d0588  mov     edx, eax
0x1400d058a  movzx   eax, byte ptr [rbx+40h]
0x1400d058e  and     edx, 3Fh
0x1400d0591  cmp     edx, eax
0x1400d0593  jb      short loc_1400D05AB
0x1400d0595  jz      short loc_1400D05A9
0x1400d0597  cmp     al, 1
0x1400d0599  jz      short loc_1400D05A9
0x1400d059b  sub     edx, eax
0x1400d059d  mov     rax, [rbx+38h]
0x1400d05a1  dec     edx
0x1400d05a3  movzx   edx, byte ptr [rdx+rax]
0x1400d05a7  jmp     short loc_1400D05AB
0x1400d05a9  xor     edx, edx
0x1400d05ab  mov     [rsp+28h+arg_0], 0
0x1400d05b4  mov     eax, edx
0x1400d05b6  shl     rax, 8
0x1400d05ba  add     rax, 5C0h
0x1400d05c0  mov     byte ptr [rsp+28h+arg_0+4], dl
0x1400d05c4  mov     rdx, gs:0
0x1400d05cd  mov     ecx, [rbx+4Ch]
0x1400d05d0  shr     rax, 6
0x1400d05d4  mov     word ptr [rsp+28h+arg_0], ax
0x1400d05d9  dec     ecx
0x1400d05db  mov     eax, 3
0x1400d05e0  mov     word ptr [rsp+28h+arg_0+2], ax
0x1400d05e5  mov     rax, [rsp+28h+arg_0]
0x1400d05ea  mov     [rdx+rcx*8+0B68h], rax
0x1400d05f2  add     rsp, 20h
0x1400d05f6  pop     rbx
0x1400d05f7  retn
```
