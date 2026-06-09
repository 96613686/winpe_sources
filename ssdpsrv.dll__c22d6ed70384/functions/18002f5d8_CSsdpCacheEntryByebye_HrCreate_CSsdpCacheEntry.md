# CSsdpCacheEntryByebye::HrCreate(CSsdpCacheEntry *)

- ea: `0x18002f5d8`
- end: `0x18002f677`
- name: `?HrCreate@CSsdpCacheEntryByebye@@SAJPEAVCSsdpCacheEntry@@@Z`
- size: `159`
- prototype: `__int64 __fastcall(struct CSsdpCacheEntry *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180025ea0`

## callees

- `0x180001798`
- `0x1800255a8`
- `0x18002f5d8`
- `0x180036010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002f5ea`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002f5ea`

## pseudocode

```c
__int64 __fastcall CSsdpCacheEntryByebye::HrCreate(struct CSsdpCacheEntry *a1)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rax
  int v3; // edx
  void (__fastcall ***v4)(_QWORD, __int64); // rdi
  int v5; // eax
  unsigned int v6; // ebx

  v2 = (void (__fastcall ***)(_QWORD, __int64))malloc(0x18u);
  v4 = v2;
  if ( v2 )
  {
    *((_DWORD *)v2 + 2) = 0;
    v2[2] = (void (__fastcall **)(_QWORD, __int64))a1;
    *v2 = (void (__fastcall **)(_QWORD, __int64))&CSsdpCacheEntryByebye::`vftable';
    v5 = CWorkItem::HrStart(v2, v3);
    v6 = v5;
    if ( v5 >= 0 )
    {
      if ( !v5 )
        return v6;
    }
    else
    {
      (**v4)(v4, 1);
    }
  }
  else
  {
    v6 = -2147024882;
  }
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18002f5d8  mov     [rsp+arg_0], rbx
0x18002f5dd  push    rdi
0x18002f5de  sub     rsp, 20h
0x18002f5e2  mov     rbx, rcx
0x18002f5e5  mov     ecx, 18h; Size
0x18002f5ea  call    cs:__imp_malloc
0x18002f5f0  mov     rdi, rax
0x18002f5f3  test    rax, rax
0x18002f5f6  jz      short loc_18002F634
0x18002f5f8  mov     dword ptr [rax+8], 0
0x18002f5ff  mov     rcx, rdi; pv
0x18002f602  lea     rax, ??_7CSsdpCacheEntryByebye@@6B@; const CSsdpCacheEntryByebye::`vftable'
0x18002f609  mov     [rdi+10h], rbx
0x18002f60d  mov     [rdi], rax
0x18002f610  call    ?HrStart@CWorkItem@@QEAAJH@Z; CWorkItem::HrStart(int)
0x18002f615  mov     ebx, eax
0x18002f617  test    eax, eax
0x18002f619  jns     short loc_18002F630
0x18002f61b  mov     rcx, [rdi]
0x18002f61e  mov     edx, 1
0x18002f623  mov     rax, [rcx]
0x18002f626  mov     rcx, rdi
0x18002f629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f62e  jmp     short loc_18002F639
0x18002f630  jz      short loc_18002F66A
0x18002f632  jmp     short loc_18002F639
0x18002f634  mov     ebx, 8007000Eh
0x18002f639  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f640  lea     rax, WPP_GLOBAL_Control
0x18002f647  cmp     rcx, rax
0x18002f64a  jz      short loc_18002F66A
0x18002f64c  test    byte ptr [rcx+1Ch], 1
0x18002f650  jz      short loc_18002F66A
0x18002f652  mov     rcx, [rcx+10h]
0x18002f656  lea     r8, WPP_3407a6ab4c9c31c56e51c47668d4e396_Traceguids
0x18002f65d  mov     edx, 0Eh
0x18002f662  mov     r9d, ebx
0x18002f665  call    WPP_SF_d
0x18002f66a  mov     eax, ebx
0x18002f66c  mov     rbx, [rsp+28h+arg_0]
0x18002f671  add     rsp, 20h
0x18002f675  pop     rdi
0x18002f676  retn
```
