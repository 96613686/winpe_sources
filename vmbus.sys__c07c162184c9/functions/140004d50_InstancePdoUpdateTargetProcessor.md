# InstancePdoUpdateTargetProcessor

- ea: `0x140004d50`
- end: `0x140004de3`
- name: `InstancePdoUpdateTargetProcessor`
- size: `147`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400043c8`
- `0x140004f40`
- `0x14000b800`
- `0x140029c10`

## callees

- `0x140004d50`

## pseudocode

```c
void __fastcall InstancePdoUpdateTargetProcessor(__int64 a1, unsigned int a2)
{
  _BYTE *v2; // r9
  unsigned int *v3; // r8
  __int64 v5; // rax
  unsigned __int16 *v6; // rcx
  _BYTE *v7; // r10
  __int64 v8; // rcx

  v2 = (_BYTE *)(a1 + 348);
  v3 = (unsigned int *)(a1 + 344);
  if ( *(_BYTE *)(a1 + 348) )
  {
    v5 = *v3;
    v6 = (unsigned __int16 *)VmbusProcessors;
    --*((_DWORD *)VmbusProcessors + 2 * v5 + 1);
    if ( (_DWORD)v5 )
    {
      --*((_DWORD *)VmbusNodes + 8 * v6[4 * v5] + 7);
      v7 = (_BYTE *)(a1 + 348);
    }
    else
    {
      v7 = v2;
    }
    *v3 = 0;
    *v2 = 0;
  }
  else
  {
    v7 = (_BYTE *)(a1 + 348);
  }
  if ( a2 < VmbusProcessorCount )
  {
    ++*((_DWORD *)VmbusProcessors + 2 * a2 + 1);
    if ( a2 )
    {
      _mm_lfence();
      v8 = 32LL * *((unsigned __int16 *)VmbusProcessors + 4 * a2);
      ++*(_DWORD *)((char *)VmbusNodes + v8 + 28);
    }
    *v3 = a2;
    *v7 = 1;
  }
}

```

## disassembly

```asm
0x140004d50  lea     r9, [rcx+15Ch]
0x140004d57  xor     r11d, r11d
0x140004d5a  lea     r8, [rcx+158h]
0x140004d61  mov     r10, rcx
0x140004d64  cmp     [r9], r11b
0x140004d67  jz      short loc_140004DA2
0x140004d69  mov     eax, [r8]
0x140004d6c  mov     rcx, cs:VmbusProcessors
0x140004d73  dec     dword ptr [rcx+rax*8+4]
0x140004d77  test    eax, eax
0x140004d79  jz      short loc_140004D97
0x140004d7b  movzx   ecx, word ptr [rcx+rax*8]
0x140004d7f  mov     rax, cs:VmbusNodes
0x140004d86  shl     rcx, 5
0x140004d8a  dec     dword ptr [rcx+rax+1Ch]
0x140004d8e  add     r10, 15Ch
0x140004d95  jmp     short loc_140004D9A
0x140004d97  mov     r10, r9
0x140004d9a  mov     [r8], r11d
0x140004d9d  mov     [r9], r11b
0x140004da0  jmp     short loc_140004DA5
0x140004da2  mov     r10, r9
0x140004da5  cmp     edx, cs:VmbusProcessorCount
0x140004dab  jnb     short locret_140004DE2
0x140004dad  mov     rax, cs:VmbusProcessors
0x140004db4  mov     ecx, edx
0x140004db6  inc     dword ptr [rax+rcx*8+4]
0x140004dba  test    edx, edx
0x140004dbc  jz      short loc_140004DDB
0x140004dbe  lfence
0x140004dc1  mov     rax, cs:VmbusProcessors
0x140004dc8  movzx   ecx, word ptr [rax+rcx*8]
0x140004dcc  mov     rax, cs:VmbusNodes
0x140004dd3  shl     rcx, 5
0x140004dd7  inc     dword ptr [rcx+rax+1Ch]
0x140004ddb  mov     [r8], edx
0x140004dde  mov     byte ptr [r10], 1
0x140004de2  retn
```
