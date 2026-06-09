# HrIsBaseOSComponent(_GUID const *,int *)

- ea: `0x180007aa8`
- end: `0x180007b21`
- name: `?HrIsBaseOSComponent@@YAJPEBU_GUID@@PEAH@Z`
- size: `121`
- prototype: `__int64 __fastcall(const struct _GUID *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009ca0`

## callees

- `0x180007aa8`
- `0x18000aa70`
- `0x18000ded4`

## pseudocode

```c
__int64 __fastcall HrIsBaseOSComponent(struct _GUID *a1, unsigned int *a2)
{
  unsigned int ComponentInfo; // ebx
  unsigned int v5; // [rsp+48h] [rbp+10h] BYREF

  *a2 = 0;
  v5 = 0;
  ComponentInfo = HrGetComponentInfo(a1, (enum tagXW_COMPONENT_TYPE *)a2, (BYTE *)&v5);
  if ( !ComponentInfo )
    *a2 = v5 & 0x10000;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_DD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      &WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids,
      *a2,
      ComponentInfo);
  return ComponentInfo;
}

```

## disassembly

```asm
0x180007aa8  mov     [rsp+arg_0], rbx
0x180007aad  push    rdi
0x180007aae  sub     rsp, 30h
0x180007ab2  lea     r8, [rsp+38h+arg_8]; unsigned int *
0x180007ab7  mov     dword ptr [rdx], 0
0x180007abd  mov     rdi, rdx
0x180007ac0  mov     [rsp+38h+arg_8], 0
0x180007ac8  call    ?HrGetComponentInfo@@YAJPEBU_GUID@@PEAW4tagXW_COMPONENT_TYPE@@PEAK@Z; HrGetComponentInfo(_GUID const *,tagXW_COMPONENT_TYPE *,ulong *)
0x180007acd  mov     ebx, eax
0x180007acf  test    eax, eax
0x180007ad1  jnz     short loc_180007ADF
0x180007ad3  mov     ecx, [rsp+38h+arg_8]
0x180007ad7  and     ecx, 10000h
0x180007add  mov     [rdi], ecx
0x180007adf  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ae6  lea     rax, WPP_GLOBAL_Control
0x180007aed  cmp     rcx, rax
0x180007af0  jz      short loc_180007B14
0x180007af2  test    byte ptr [rcx+1Ch], 10h
0x180007af6  jz      short loc_180007B14
0x180007af8  mov     r9d, [rdi]
0x180007afb  lea     r8, WPP_e5011644dfd53dc127bd5997e800a79d_Traceguids
0x180007b02  mov     rcx, [rcx+10h]
0x180007b06  mov     edx, 0Ah
0x180007b0b  mov     [rsp+38h+var_18], ebx
0x180007b0f  call    WPP_SF_DD
0x180007b14  mov     eax, ebx
0x180007b16  mov     rbx, [rsp+38h+arg_0]
0x180007b1b  add     rsp, 30h
0x180007b1f  pop     rdi
0x180007b20  retn
```
