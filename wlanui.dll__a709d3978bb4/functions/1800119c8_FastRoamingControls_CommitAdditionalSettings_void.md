# FastRoamingControls::CommitAdditionalSettings(void)

- ea: `0x1800119c8`
- end: `0x180011a78`
- name: `?CommitAdditionalSettings@FastRoamingControls@@QEAAJXZ`
- size: `176`
- prototype: `__int64 __fastcall(FastRoamingControls *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009380`

## callees

- `0x1800119c8`

## pseudocode

```c
__int64 __fastcall FastRoamingControls::CommitAdditionalSettings(FastRoamingControls *this)
{
  int *v2; // r9
  int v3; // eax
  int v4; // ecx
  int v5; // edx

  v2 = *(int **)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 40LL) + 552LL) + 32LL) + 424LL);
  *v2 |= 0x20u;
  v2[28] = (*((_DWORD *)this + 6) != 0) + 1;
  v3 = *v2 ^ (*v2 ^ (*((_DWORD *)this + 6) << 7)) & 0x80;
  *v2 = v3;
  v4 = v3 ^ ((unsigned __int8)v3 ^ (unsigned __int8)((unsigned __int8)*((_DWORD *)this + 6) << 6)) & 0x40;
  *v2 = v4;
  v5 = v4 ^ ((unsigned __int8)v4 ^ (unsigned __int8)(8 * *((_DWORD *)this + 6))) & 8;
  *v2 = v5;
  if ( *((_DWORD *)this + 6) )
  {
    v2[30] = 60 * *((_DWORD *)this + 7);
    v2[29] = *((_DWORD *)this + 8);
    v2[26] = (*((_DWORD *)this + 9) != 0) + 1;
    *v2 = v5 ^ ((unsigned __int8)v5 ^ (unsigned __int8)(16 * *((_DWORD *)this + 9))) & 0x10;
    if ( *((_DWORD *)this + 9) )
      v2[27] = *((_DWORD *)this + 10);
  }
  return 0;
}

```

## disassembly

```asm
0x1800119c8  mov     rax, [rcx+10h]
0x1800119cc  mov     r8, rcx
0x1800119cf  mov     rdx, [rax+28h]
0x1800119d3  mov     rax, [rdx+228h]
0x1800119da  mov     rdx, [rax+20h]
0x1800119de  mov     r9, [rdx+1A8h]
0x1800119e5  or      dword ptr [r9], 20h
0x1800119e9  mov     eax, [rcx+18h]
0x1800119ec  neg     eax
0x1800119ee  sbb     edx, edx
0x1800119f0  neg     edx
0x1800119f2  inc     edx
0x1800119f4  mov     [r9+70h], edx
0x1800119f8  mov     eax, [rcx+18h]
0x1800119fb  shl     eax, 7
0x1800119fe  xor     eax, [r9]
0x180011a01  and     eax, 80h
0x180011a06  xor     eax, [r9]
0x180011a09  mov     [r9], eax
0x180011a0c  mov     ecx, [rcx+18h]
0x180011a0f  shl     ecx, 6
0x180011a12  xor     ecx, eax
0x180011a14  and     ecx, 40h
0x180011a17  xor     ecx, eax
0x180011a19  mov     [r9], ecx
0x180011a1c  mov     edx, [r8+18h]
0x180011a20  shl     edx, 3
0x180011a23  xor     edx, ecx
0x180011a25  and     edx, 8
0x180011a28  xor     edx, ecx
0x180011a2a  mov     [r9], edx
0x180011a2d  cmp     dword ptr [r8+18h], 0
0x180011a32  jz      short loc_180011A75
0x180011a34  imul    eax, [r8+1Ch], 3Ch ; '<'
0x180011a39  mov     [r9+78h], eax
0x180011a3d  mov     eax, [r8+20h]
0x180011a41  mov     [r9+74h], eax
0x180011a45  mov     eax, [r8+24h]
0x180011a49  neg     eax
0x180011a4b  sbb     ecx, ecx
0x180011a4d  neg     ecx
0x180011a4f  inc     ecx
0x180011a51  mov     [r9+68h], ecx
0x180011a55  mov     eax, [r8+24h]
0x180011a59  shl     eax, 4
0x180011a5c  xor     eax, edx
0x180011a5e  and     eax, 10h
0x180011a61  xor     eax, edx
0x180011a63  mov     [r9], eax
0x180011a66  cmp     dword ptr [r8+24h], 0
0x180011a6b  jz      short loc_180011A75
0x180011a6d  mov     eax, [r8+28h]
0x180011a71  mov     [r9+6Ch], eax
0x180011a75  xor     eax, eax
0x180011a77  retn
```
