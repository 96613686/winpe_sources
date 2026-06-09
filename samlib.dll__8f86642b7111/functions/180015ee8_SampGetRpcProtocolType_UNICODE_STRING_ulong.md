# SampGetRpcProtocolType(_UNICODE_STRING *,ulong *)

- ea: `0x180015ee8`
- end: `0x180015f48`
- name: `?SampGetRpcProtocolType@@YAJPEAU_UNICODE_STRING@@PEAK@Z`
- size: `96`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013060`
- `0x180013490`

## callees

- `0x180015b44`
- `0x180015ee8`

## pseudocode

```c
__int64 __fastcall SampGetRpcProtocolType(struct _UNICODE_STRING *a1, unsigned int *a2)
{
  int v2; // r8d
  unsigned __int8 v3; // al
  unsigned int v5; // ebx
  unsigned __int64 v6; // r9
  unsigned __int8 v8; // [rsp+30h] [rbp+8h] BYREF

  v2 = 0;
  v3 = 0;
  v8 = 0;
  v5 = 1;
  *a2 = 1;
  if ( a1 )
  {
    v6 = (unsigned __int64)a1->Length >> 1;
    if ( v6 )
    {
      v2 = IsLocalServerName(v6, a1->Buffer, &v8);
      if ( v2 < 0 )
        return (unsigned int)v2;
      v3 = v8;
    }
  }
  if ( v3 )
    v5 = 2;
  *a2 = v5;
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180015ee8  mov     [rsp+arg_8], rbx
0x180015eed  push    rdi
0x180015eee  sub     rsp, 20h
0x180015ef2  xor     r8d, r8d
0x180015ef5  xor     al, al
0x180015ef7  mov     [rsp+28h+arg_0], al
0x180015efb  mov     rdi, rdx
0x180015efe  lea     ebx, [r8+1]
0x180015f02  mov     [rdx], ebx
0x180015f04  test    rcx, rcx
0x180015f07  jz      short loc_180015F2E
0x180015f09  movzx   r9d, word ptr [rcx]
0x180015f0d  shr     r9, 1
0x180015f10  jz      short loc_180015F2E
0x180015f12  mov     rdx, [rcx+8]; unsigned __int16 *
0x180015f16  lea     r8, [rsp+28h+arg_0]; unsigned __int8 *
0x180015f1b  mov     rcx, r9; unsigned __int64
0x180015f1e  call    ?IsLocalServerName@@YAJ_KPEAGPEAE@Z; IsLocalServerName(unsigned __int64,ushort *,uchar *)
0x180015f23  mov     r8d, eax
0x180015f26  test    eax, eax
0x180015f28  js      short loc_180015F3A
0x180015f2a  mov     al, [rsp+28h+arg_0]
0x180015f2e  test    al, al
0x180015f30  mov     ecx, 2
0x180015f35  cmovnz  ebx, ecx
0x180015f38  mov     [rdi], ebx
0x180015f3a  mov     rbx, [rsp+28h+arg_8]
0x180015f3f  mov     eax, r8d
0x180015f42  add     rsp, 20h
0x180015f46  pop     rdi
0x180015f47  retn
```
