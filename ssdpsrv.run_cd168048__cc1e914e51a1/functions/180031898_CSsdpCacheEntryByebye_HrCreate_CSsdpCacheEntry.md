# CSsdpCacheEntryByebye::HrCreate(CSsdpCacheEntry *)

- ea: `0x180031898`
- end: `0x18003193e`
- name: `?HrCreate@CSsdpCacheEntryByebye@@SAJPEAVCSsdpCacheEntry@@@Z`
- size: `166`
- prototype: `__int64 __fastcall(struct CSsdpCacheEntry *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180027c10`

## callees

- `0x180014aa4`
- `0x1800271fc`
- `0x180031898`
- `0x180039010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800318aa`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800318aa`

## pseudocode

```c
__int64 __fastcall CSsdpCacheEntryByebye::HrCreate(struct CSsdpCacheEntry *a1)
{
  _DWORD *v2; // rax
  void (__fastcall ***v3)(_QWORD, __int64); // rdi
  int v4; // eax
  unsigned int v5; // ebx

  v2 = malloc(0x18u);
  v3 = (void (__fastcall ***)(_QWORD, __int64))v2;
  if ( v2 )
  {
    v2[2] = 0;
    *((_QWORD *)v2 + 2) = a1;
    *(_QWORD *)v2 = &CSsdpCacheEntryByebye::`vftable';
    v4 = CWorkItem::HrStart(v2);
    v5 = v4;
    if ( v4 >= 0 )
    {
      if ( !v4 )
        return v5;
    }
    else
    {
      (**v3)(v3, 1);
    }
  }
  else
  {
    v5 = -2147024882;
  }
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x180031898  mov     [rsp+arg_0], rbx
0x18003189d  push    rdi
0x18003189e  sub     rsp, 20h
0x1800318a2  mov     rbx, rcx
0x1800318a5  mov     ecx, 18h; Size
0x1800318aa  call    cs:__imp_malloc
0x1800318b1  nop     dword ptr [rax+rax+00h]
0x1800318b6  mov     rdi, rax
0x1800318b9  test    rax, rax
0x1800318bc  jz      short loc_1800318FA
0x1800318be  mov     dword ptr [rax+8], 0
0x1800318c5  mov     rcx, rdi; pv
0x1800318c8  lea     rax, ??_7CSsdpCacheEntryByebye@@6B@; const CSsdpCacheEntryByebye::`vftable'
0x1800318cf  mov     [rdi+10h], rbx
0x1800318d3  mov     [rdi], rax
0x1800318d6  call    ?HrStart@CWorkItem@@QEAAJH@Z; CWorkItem::HrStart(int)
0x1800318db  mov     ebx, eax
0x1800318dd  test    eax, eax
0x1800318df  jns     short loc_1800318F6
0x1800318e1  mov     rcx, [rdi]
0x1800318e4  mov     edx, 1
0x1800318e9  mov     rax, [rcx]
0x1800318ec  mov     rcx, rdi
0x1800318ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800318f4  jmp     short loc_1800318FF
0x1800318f6  jz      short loc_180031930
0x1800318f8  jmp     short loc_1800318FF
0x1800318fa  mov     ebx, 8007000Eh
0x1800318ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180031906  lea     rax, WPP_GLOBAL_Control
0x18003190d  cmp     rcx, rax
0x180031910  jz      short loc_180031930
0x180031912  test    byte ptr [rcx+1Ch], 1
0x180031916  jz      short loc_180031930
0x180031918  mov     rcx, [rcx+10h]
0x18003191c  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x180031923  mov     edx, 0Eh
0x180031928  mov     r9d, ebx
0x18003192b  call    WPP_SF_d
0x180031930  mov     eax, ebx
0x180031932  mov     rbx, [rsp+28h+arg_0]
0x180031937  add     rsp, 20h
0x18003193b  pop     rdi
0x18003193c  retn
```
