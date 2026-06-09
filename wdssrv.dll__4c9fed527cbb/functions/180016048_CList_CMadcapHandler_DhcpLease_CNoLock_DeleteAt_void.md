# CList<CMadcapHandler::DhcpLease,CNoLock>::DeleteAt(void * &)

- ea: `0x180016048`
- end: `0x1800160e0`
- name: `?DeleteAt@?$CList@UDhcpLease@CMadcapHandler@@VCNoLock@@@@QEAAPEAUDhcpLease@CMadcapHandler@@AEAPEAX@Z`
- size: `152`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180016da4`
- `0x1800171d0`

## callees

- `0x180016048`

## pseudocode

```c
__int64 __fastcall CList<CMadcapHandler::DhcpLease,CNoLock>::DeleteAt(__int64 *a1, __int64 *a2)
{
  __int64 v2; // r9
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx

  v2 = *a2;
  if ( *a2 )
  {
    v5 = *a1;
    v6 = a1[1];
    if ( v5 == v6 )
    {
      a1[1] = 0;
      *a1 = 0;
    }
    else
    {
      if ( v2 == v5 )
      {
        v7 = *(_QWORD *)(v5 + 232);
        *a1 = v7;
        *(_QWORD *)(v7 + 240) = 0;
        *a2 = *a1;
LABEL_10:
        --*((_DWORD *)a1 + 5);
        return v2;
      }
      if ( v2 != v6 )
      {
        v9 = *(_QWORD *)(v2 + 232);
        v10 = *(_QWORD *)(v2 + 240);
        *a2 = v9;
        *(_QWORD *)(v10 + 232) = v9;
        *(_QWORD *)(*(_QWORD *)(v2 + 232) + 240LL) = *(_QWORD *)(v2 + 240);
        goto LABEL_10;
      }
      v8 = *(_QWORD *)(v6 + 240);
      a1[1] = v8;
      *(_QWORD *)(v8 + 232) = 0;
    }
    *a2 = 0;
    goto LABEL_10;
  }
  return v2;
}

```

## disassembly

```asm
0x180016048  mov     r9, [rdx]
0x18001604b  mov     r10, rdx
0x18001604e  xor     edx, edx
0x180016050  mov     r8, rcx
0x180016053  test    r9, r9
0x180016056  jz      loc_1800160DC
0x18001605c  mov     rax, [rcx]
0x18001605f  mov     rcx, [rcx+8]
0x180016063  cmp     rax, rcx
0x180016066  jnz     short loc_180016071
0x180016068  mov     [r8+8], rdx
0x18001606c  mov     [r8], rdx
0x18001606f  jmp     short loc_1800160A6
0x180016071  cmp     r9, rax
0x180016074  jnz     short loc_18001608F
0x180016076  mov     rax, [rax+0E8h]
0x18001607d  mov     [r8], rax
0x180016080  mov     [rax+0F0h], rdx
0x180016087  mov     rax, [r8]
0x18001608a  mov     [r10], rax
0x18001608d  jmp     short loc_1800160D8
0x18001608f  cmp     r9, rcx
0x180016092  jnz     short loc_1800160AB
0x180016094  mov     rax, [rcx+0F0h]
0x18001609b  mov     [r8+8], rax
0x18001609f  mov     [rax+0E8h], rdx
0x1800160a6  mov     [r10], rdx
0x1800160a9  jmp     short loc_1800160D8
0x1800160ab  mov     rdx, [r9+0E8h]
0x1800160b2  mov     rcx, [r9+0F0h]
0x1800160b9  mov     [r10], rdx
0x1800160bc  mov     [rcx+0E8h], rdx
0x1800160c3  mov     rdx, [r9+0E8h]
0x1800160ca  mov     rcx, [r9+0F0h]
0x1800160d1  mov     [rdx+0F0h], rcx
0x1800160d8  dec     dword ptr [r8+14h]
0x1800160dc  mov     rax, r9
0x1800160df  retn
```
