# GetTmfSearchPath

- ea: `0x140038570`
- end: `0x1400386f9`
- name: `GetTmfSearchPath`
- size: `393`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140038924`
- `0x140038c18`

## callees

- `0x140002bf0`
- `0x140038408`
- `0x140038570`
- `0x1400387a4`
- `0x140038850`

## import_xrefs

- `msvcrt!fprintf` at `0x140038691`
- `msvcrt!fprintf` at `0x140038691`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x1400385b1`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x140038633`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x1400385b1`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x140038633`

## string_xrefs

- `0x140038599`: `TRACE_FORMAT_SEARCH_PATH`
- `0x14003868a`: `Could not get the current directory\n`

## pseudocode

```c
__int64 __fastcall GetTmfSearchPath(__int64 a1, _WORD *a2)
{
  _QWORD *v2; // rbx
  DWORD CurrentDirectoryW; // eax
  unsigned __int64 v5; // rbp
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // rax
  __int64 v8; // rax
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rdx
  DWORD v11; // eax
  LPWSTR v12; // rdx
  unsigned __int64 v13; // rcx
  WCHAR *v14; // rcx
  FILE *v15; // rax
  unsigned __int64 v16; // rax
  unsigned __int64 v17; // r8
  unsigned __int64 v18; // r9
  _WORD *v19; // rcx

  v2 = (_QWORD *)(a1 + 16);
  *(_QWORD *)a1 = a1 + 16;
  *(_QWORD *)(a1 + 8) = a1 + 16;
  *(_WORD *)(a1 + 16) = 0;
  if ( a2 )
  {
    v16 = -1;
    v17 = -1;
    do
      ++v17;
    while ( a2[v17] );
    if ( v17 )
    {
      v18 = v17;
      v19 = a2;
      if ( *a2 == 59 )
      {
LABEL_35:
        v16 = v19 - a2;
      }
      else
      {
        while ( v18 != 1 )
        {
          ++v19;
          --v18;
          if ( *v19 == 59 )
          {
            if ( !v19 )
              break;
            goto LABEL_35;
          }
        }
      }
    }
    if ( v17 >= v16 )
      v17 = v16;
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
      a1,
      a2,
      v17);
  }
  else
  {
    if ( (int)tlx::assign_environment_variable<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
                a1,
                L"TRACE_FORMAT_SEARCH_PATH") >= 0 )
      return a1;
    CurrentDirectoryW = GetCurrentDirectoryW(0, 0);
    v5 = CurrentDirectoryW;
    if ( !CurrentDirectoryW )
      goto LABEL_27;
    v6 = 7;
    if ( *(_QWORD **)a1 == v2 )
      v7 = 7;
    else
      v7 = (__int64)(*v2 - *(_QWORD *)a1) >> 1;
    if ( v5 <= v7 )
      goto LABEL_17;
    if ( *(_QWORD **)a1 == v2 )
      v8 = 7;
    else
      v8 = (__int64)(*v2 - *(_QWORD *)a1) >> 1;
    v9 = 2 * v8 + 1;
    v10 = v5;
    if ( v9 >= v5 )
      v10 = v9;
    if ( v10 > 0x3FFFFFFFFFFFFFF7LL )
      v10 = 0x3FFFFFFFFFFFFFF7LL;
    if ( v5 <= v10
      && (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_GrowTo(a1) )
    {
LABEL_17:
      v11 = GetCurrentDirectoryW(v5, *(LPWSTR *)a1);
      if ( v11 )
      {
        v12 = *(LPWSTR *)a1;
        v13 = *(_QWORD **)a1 == v2 ? 7LL : (__int64)(*v2 - (_QWORD)v12) >> 1;
        if ( v11 <= v13 )
        {
          if ( v12 != (LPWSTR)v2 )
            v6 = (__int64)(*v2 - (_QWORD)v12) >> 1;
          if ( v11 > v6 )
            __int2c();
          v14 = &v12[v11];
          *(_QWORD *)(a1 + 8) = v14;
          *v14 = 0;
          return a1;
        }
      }
LABEL_27:
      v15 = _acrt_iob_func(1u);
      fprintf(v15, "Could not get the current directory\n");
    }
  }
  return a1;
}

```

## disassembly

```asm
0x140038570  push    rbx
0x140038572  push    rbp
0x140038573  push    rsi
0x140038574  push    rdi
0x140038575  push    r14
0x140038577  sub     rsp, 20h
0x14003857b  lea     rbx, [rcx+10h]
0x14003857f  xor     r14d, r14d
0x140038582  mov     [rcx], rbx
0x140038585  mov     rdi, rcx
0x140038588  mov     [rcx+8], rbx
0x14003858c  mov     [rbx], r14w
0x140038590  test    rdx, rdx
0x140038593  jnz     loc_140038699
0x140038599  lea     rdx, aTraceFormatSea; "TRACE_FORMAT_SEARCH_PATH"
0x1400385a0  call    ??$assign_environment_variable@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBG@Z; tlx::assign_environment_variable<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *)
0x1400385a5  test    eax, eax
0x1400385a7  jns     loc_1400386EB
0x1400385ad  xor     edx, edx; lpBuffer
0x1400385af  xor     ecx, ecx; nBufferLength
0x1400385b1  call    cs:__imp_GetCurrentDirectoryW
0x1400385b7  mov     ebp, eax
0x1400385b9  test    eax, eax
0x1400385bb  jz      loc_14003867D
0x1400385c1  lea     esi, [r14+7]
0x1400385c5  cmp     [rdi], rbx
0x1400385c8  jnz     short loc_1400385CE
0x1400385ca  mov     eax, esi
0x1400385cc  jmp     short loc_1400385D7
0x1400385ce  mov     rax, [rbx]
0x1400385d1  sub     rax, [rdi]
0x1400385d4  sar     rax, 1
0x1400385d7  mov     rcx, rbp
0x1400385da  cmp     rbp, rax
0x1400385dd  jbe     short loc_14003862E
0x1400385df  cmp     [rdi], rbx
0x1400385e2  jnz     short loc_1400385E9
0x1400385e4  mov     rax, rsi
0x1400385e7  jmp     short loc_1400385F2
0x1400385e9  mov     rax, [rbx]
0x1400385ec  sub     rax, [rdi]
0x1400385ef  sar     rax, 1
0x1400385f2  lea     rax, ds:1[rax*2]
0x1400385fa  mov     rdx, rcx
0x1400385fd  cmp     rax, rcx
0x140038600  cmovnb  rdx, rax
0x140038604  mov     rax, 3FFFFFFFFFFFFFF7h
0x14003860e  cmp     rdx, rax
0x140038611  cmova   rdx, rax
0x140038615  cmp     rcx, rdx
0x140038618  ja      loc_1400386EB
0x14003861e  mov     rcx, rdi
0x140038621  call    ?_GrowTo@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAA_N_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_GrowTo(unsigned __int64)
0x140038626  test    al, al
0x140038628  jz      loc_1400386EB
0x14003862e  mov     rdx, [rdi]; lpBuffer
0x140038631  mov     ecx, ebp; nBufferLength
0x140038633  call    cs:__imp_GetCurrentDirectoryW
0x140038639  test    eax, eax
0x14003863b  jz      short loc_14003867D
0x14003863d  mov     rdx, [rdi]
0x140038640  cmp     rdx, rbx
0x140038643  jnz     short loc_14003864A
0x140038645  mov     rcx, rsi
0x140038648  jmp     short loc_140038653
0x14003864a  mov     rcx, [rbx]
0x14003864d  sub     rcx, rdx
0x140038650  sar     rcx, 1
0x140038653  mov     eax, eax
0x140038655  cmp     rax, rcx
0x140038658  ja      short loc_14003867D
0x14003865a  cmp     rdx, rbx
0x14003865d  jz      short loc_140038668
0x14003865f  mov     rsi, [rbx]
0x140038662  sub     rsi, rdx
0x140038665  sar     rsi, 1
0x140038668  cmp     rax, rsi
0x14003866b  jbe     short loc_14003866F
0x14003866d  int     2Ch; Windows NT - assertion failure
0x14003866f  lea     rcx, [rdx+rax*2]
0x140038673  mov     [rdi+8], rcx
0x140038677  mov     [rcx], r14w
0x14003867b  jmp     short loc_1400386EB
0x14003867d  mov     ecx, 1; Ix
0x140038682  call    __acrt_iob_func
0x140038687  mov     rcx, rax; Stream
0x14003868a  lea     rdx, aCouldNotGetThe; "Could not get the current directory\n"
0x140038691  call    cs:__imp_fprintf
0x140038697  jmp     short loc_1400386EB
0x140038699  or      rax, 0FFFFFFFFFFFFFFFFh
0x14003869d  mov     r8, rax
0x1400386a0  inc     r8
0x1400386a3  cmp     [rdx+r8*2], r14w
0x1400386a8  jnz     short loc_1400386A0
0x1400386aa  test    r8, r8
0x1400386ad  jz      short loc_1400386DC
0x1400386af  cmp     word ptr [rdx], 3Bh ; ';'
0x1400386b3  mov     r9, r8
0x1400386b6  mov     rcx, rdx
0x1400386b9  jz      short loc_1400386D3
0x1400386bb  cmp     r9, 1
0x1400386bf  jz      short loc_1400386DC
0x1400386c1  add     rcx, 2
0x1400386c5  dec     r9
0x1400386c8  cmp     word ptr [rcx], 3Bh ; ';'
0x1400386cc  jnz     short loc_1400386BB
0x1400386ce  test    rcx, rcx
0x1400386d1  jz      short loc_1400386DC
0x1400386d3  mov     rax, rcx
0x1400386d6  sub     rax, rdx
0x1400386d9  sar     rax, 1
0x1400386dc  cmp     r8, rax
0x1400386df  mov     rcx, rdi
0x1400386e2  cmovnb  r8, rax
0x1400386e6  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1400386eb  mov     rax, rdi
0x1400386ee  add     rsp, 20h
0x1400386f2  pop     r14
0x1400386f4  pop     rdi
0x1400386f5  pop     rsi
0x1400386f6  pop     rbp
0x1400386f7  pop     rbx
0x1400386f8  retn
```
