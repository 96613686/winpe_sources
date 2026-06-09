# IsCompressedVideoFormat

- ea: `0x1800054e0`
- end: `0x1800055cc`
- name: `IsCompressedVideoFormat`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003c80`

## callees

- `0x1800054e0`

## pseudocode

```c
__int64 __fastcall IsCompressedVideoFormat(__int64 a1)
{
  unsigned int v1; // edx
  unsigned int v2; // ecx

  v1 = 1;
  if ( *(_QWORD *)(a1 + 4) != *(_QWORD *)&MFVideoFormat_Base.Data2
    || *(_DWORD *)(a1 + 12) != *(_DWORD *)&MFVideoFormat_Base.Data4[4] )
  {
    return v1;
  }
  v2 = *(_DWORD *)a1;
  if ( v2 > 0x32315659 )
  {
    if ( v2 != 1448433993
      && v2 != 1345401945
      && v2 != 844715353
      && v2 != 909193814
      && v2 != 961893977
      && v2 != 1431918169
      && v2 != 1448433985
      && v2 + 466162822 > 4
      && v2 != 1498831189 )
    {
      return v1;
    }
  }
  else if ( v2 != 842094169 )
  {
    if ( v2 > 0x30313276 )
    {
      if ( v2 != 825308249
        && v2 != 808531030
        && v2 != 808596553
        && v2 != 825307737
        && v2 != 825316942
        && v2 != 842094158 )
      {
        return 1;
      }
    }
    else if ( v2 != 808530550 )
    {
      switch ( v2 )
      {
        case 0u:
        case 3u:
        case 0x14u:
        case 0x16u:
        case 0x17u:
        case 0x18u:
        case 0x29u:
          return 0;
        default:
          return v1;
      }
      return v1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800054e0  mov     rax, [rcx+4]
0x1800054e4  mov     edx, 1
0x1800054e9  cmp     rax, qword ptr cs:MFVideoFormat_Base.Data2
0x1800054f0  jnz     def_180005547; jumptable 0000000180005547 default case, cases 1,2,4-19,21,25-40
0x1800054f6  mov     eax, [rcx+0Ch]
0x1800054f9  cmp     eax, dword ptr cs:MFVideoFormat_Base.Data4+4
0x1800054ff  jnz     def_180005547; jumptable 0000000180005547 default case, cases 1,2,4-19,21,25-40
0x180005505  mov     ecx, [rcx]
0x180005507  cmp     ecx, 32315659h
0x18000550d  ja      short loc_18000557C
0x18000550f  jz      loc_1800055C7; jumptable 0000000180005547 cases 0,3,20,22-24,41
0x180005515  cmp     ecx, 30313276h
0x18000551b  ja      short loc_180005549
0x18000551d  jz      loc_1800055C7; jumptable 0000000180005547 cases 0,3,20,22-24,41
0x180005523  cmp     ecx, 29h; switch 42 cases
0x180005526  ja      def_180005547; jumptable 0000000180005547 default case, cases 1,2,4-19,21,25-40
0x18000552c  lea     r8, __ImageBase
0x180005533  movzx   eax, ds:(byte_1800055D4 - 180000000h)[r8+rcx]
0x18000553c  mov     ecx, ds:(jpt_180005547 - 180000000h)[r8+rax*4]
0x180005544  add     rcx, r8
0x180005547  jmp     rcx; switch jump
0x180005549  cmp     ecx, 31313459h
0x18000554f  jz      short loc_1800055C7; jumptable 0000000180005547 cases 0,3,20,22-24,41
0x180005551  cmp     ecx, 30313456h
0x180005557  jz      short loc_1800055C7; jumptable 0000000180005547 cases 0,3,20,22-24,41
0x180005559  cmp     ecx, 30323449h
0x18000555f  jz      short loc_1800055C7; jumptable 0000000180005547 cases 0,3,20,22-24,41
0x180005561  cmp     ecx, 31313259h
0x180005567  jz      short loc_1800055C7; jumptable 0000000180005547 cases 0,3,20,22-24,41
0x180005569  cmp     ecx, 3131564Eh
0x18000556f  jz      short loc_1800055C7; jumptable 0000000180005547 cases 0,3,20,22-24,41
0x180005571  cmp     ecx, 3231564Eh
0x180005577  jz      short loc_1800055C7; jumptable 0000000180005547 cases 0,3,20,22-24,41
0x180005579  mov     eax, edx
0x18000557b  retn
0x18000557c  cmp     ecx, 56555949h
0x180005582  jz      short loc_1800055C7; jumptable 0000000180005547 cases 0,3,20,22-24,41
0x180005584  cmp     ecx, 50313459h
0x18000558a  jz      short loc_1800055C7; jumptable 0000000180005547 cases 0,3,20,22-24,41
0x18000558c  cmp     ecx, 32595559h
0x180005592  jz      short loc_1800055C7; jumptable 0000000180005547 cases 0,3,20,22-24,41
0x180005594  cmp     ecx, 36313256h
0x18000559a  jz      short loc_1800055C7; jumptable 0000000180005547 cases 0,3,20,22-24,41
0x18000559c  cmp     ecx, 39555659h
0x1800055a2  jz      short loc_1800055C7; jumptable 0000000180005547 cases 0,3,20,22-24,41
0x1800055a4  cmp     ecx, 55595659h
0x1800055aa  jz      short loc_1800055C7; jumptable 0000000180005547 cases 0,3,20,22-24,41
0x1800055ac  cmp     ecx, 56555941h
0x1800055b2  jz      short loc_1800055C7; jumptable 0000000180005547 cases 0,3,20,22-24,41
0x1800055b4  lea     eax, [rcx+1BC91486h]
0x1800055ba  cmp     eax, 4
0x1800055bd  jbe     short loc_1800055C7; jumptable 0000000180005547 cases 0,3,20,22-24,41
0x1800055bf  cmp     ecx, 59565955h
0x1800055c5  jnz     short def_180005547; jumptable 0000000180005547 default case, cases 1,2,4-19,21,25-40
0x1800055c7  xor     edx, edx; jumptable 0000000180005547 cases 0,3,20,22-24,41
0x1800055c9  mov     eax, edx; jumptable 0000000180005547 default case, cases 1,2,4-19,21,25-40
0x1800055cb  retn
```
