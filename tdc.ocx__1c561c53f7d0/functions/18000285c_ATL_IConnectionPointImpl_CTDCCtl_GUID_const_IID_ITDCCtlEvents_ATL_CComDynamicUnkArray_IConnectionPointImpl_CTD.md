# ATL::IConnectionPointImpl<CTDCCtl,&_GUID const IID_ITDCCtlEvents,ATL::CComDynamicUnkArray>::~IConnectionPointImpl<CTDCCtl,&_GUID const IID_ITDCCtlEvents,ATL::CComDynamicUnkArray>(void)

- ea: `0x18000285c`
- end: `0x1800028c1`
- name: `??1?$IConnectionPointImpl@VCTDCCtl@@$1?IID_ITDCCtlEvents@@3U_GUID@@BVCComDynamicUnkArray@ATL@@@ATL@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002970`

## callees

- `0x18000285c`
- `0x180015010`

## import_xrefs

- `msvcrt!free` at `0x1800028b0`
- `msvcrt!free` at `0x1800028b0`

## pseudocode

```c
void __fastcall ATL::IConnectionPointImpl<CTDCCtl,&_GUID const IID_ITDCCtlEvents,ATL::CComDynamicUnkArray>::~IConnectionPointImpl<CTDCCtl,&_GUID const IID_ITDCCtlEvents,ATL::CComDynamicUnkArray>(
        __int64 a1)
{
  char *v1; // rbx
  __int64 v3; // r8
  char *v4; // rdx

  v1 = *(char **)(a1 + 8);
  v3 = *(int *)(a1 + 16);
  if ( v1 >= &v1[8 * v3] )
  {
    v4 = *(char **)(a1 + 8);
  }
  else
  {
    do
    {
      if ( *(_QWORD *)v1 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v1 + 16LL))(*(_QWORD *)v1);
      v3 = *(int *)(a1 + 16);
      v1 += 8;
      v4 = *(char **)(a1 + 8);
    }
    while ( v1 < &v4[8 * v3] );
  }
  if ( (int)v3 > 0 )
    free(v4);
}

```

## disassembly

```asm
0x18000285c  mov     [rsp+arg_0], rbx
0x180002861  push    rdi
0x180002862  sub     rsp, 20h
0x180002866  mov     rbx, [rcx+8]
0x18000286a  mov     rdi, rcx
0x18000286d  movsxd  r8, dword ptr [rcx+10h]
0x180002871  lea     rdx, [rbx+r8*8]
0x180002875  cmp     rbx, rdx
0x180002878  jnb     short loc_1800028A5
0x18000287a  mov     rcx, [rbx]
0x18000287d  test    rcx, rcx
0x180002880  jz      short loc_18000288E
0x180002882  mov     rax, [rcx]
0x180002885  mov     rax, [rax+10h]
0x180002889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000288e  movsxd  r8, dword ptr [rdi+10h]
0x180002892  add     rbx, 8
0x180002896  mov     rdx, [rdi+8]
0x18000289a  lea     rcx, [rdx+r8*8]
0x18000289e  cmp     rbx, rcx
0x1800028a1  jb      short loc_18000287A
0x1800028a3  jmp     short loc_1800028A8
0x1800028a5  mov     rdx, rbx
0x1800028a8  test    r8d, r8d
0x1800028ab  jle     short loc_1800028B6
0x1800028ad  mov     rcx, rdx; Block
0x1800028b0  call    cs:__imp_free
0x1800028b6  mov     rbx, [rsp+28h+arg_0]
0x1800028bb  add     rsp, 20h
0x1800028bf  pop     rdi
0x1800028c0  retn
```
