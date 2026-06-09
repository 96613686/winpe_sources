# UpdateRealTimeWindowInformation

- ea: `0x140014f68`
- end: `0x140014fb5`
- name: `UpdateRealTimeWindowInformation`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400120b4`
- `0x140012efc`

## callees

- `0x140014f68`

## pseudocode

```c
__int64 __fastcall UpdateRealTimeWindowInformation(__int64 a1, int a2, int a3)
{
  __int64 v3; // r9
  unsigned int v4; // edx
  __int64 result; // rax

  v3 = *(_QWORD *)(a1 + 48);
  v4 = a2 - a3 + 1;
  result = v4 - *(_DWORD *)(v3 + 760);
  if ( (int)(v4 - *(_DWORD *)(v3 + 760)) > 0 )
    *(_QWORD *)(v3 + 760) = v4;
  if ( a3 )
  {
    if ( !*(_QWORD *)(v3 + 752) || (int)(v4 - *(_DWORD *)(v3 + 752)) < 0 )
      *(_QWORD *)(v3 + 752) = v4;
    *(_QWORD *)(v3 + 784) += v4;
    ++*(_QWORD *)(v3 + 792);
  }
  return result;
}

```

## disassembly

```asm
0x140014f68  mov     r9, [rcx+30h]
0x140014f6c  sub     edx, r8d
0x140014f6f  inc     edx
0x140014f71  mov     eax, edx
0x140014f73  mov     ecx, edx
0x140014f75  sub     eax, [r9+2F8h]
0x140014f7c  test    eax, eax
0x140014f7e  jle     short loc_140014F87
0x140014f80  mov     [r9+2F8h], rcx
0x140014f87  test    r8d, r8d
0x140014f8a  jz      short locret_140014FB4
0x140014f8c  cmp     qword ptr [r9+2F0h], 0
0x140014f94  jz      short loc_140014F9F
0x140014f96  cmp     edx, [r9+2F0h]
0x140014f9d  jns     short loc_140014FA6
0x140014f9f  mov     [r9+2F0h], rcx
0x140014fa6  add     [r9+310h], rcx
0x140014fad  inc     qword ptr [r9+318h]
0x140014fb4  retn
```
