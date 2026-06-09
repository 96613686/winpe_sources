# ValidateUSBInterfaceAssociationDescriptor

- ea: `0x14000e994`
- end: `0x14000ea88`
- name: `ValidateUSBInterfaceAssociationDescriptor`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000fb68`

## callees

- `0x14000a6cc`
- `0x14000e994`

## pseudocode

```c
bool __fastcall ValidateUSBInterfaceAssociationDescriptor(__int64 a1, _QWORD *a2)
{
  char v2; // al
  unsigned __int16 v4; // r8
  int v5; // edi
  unsigned __int16 v6; // r11
  __int64 v7; // rbx
  unsigned __int16 v8; // r10
  unsigned __int16 v9; // r9
  unsigned __int16 i; // r8
  __int64 v11; // rcx

  v2 = *(_BYTE *)a1;
  if ( *(_BYTE *)a1 == 8 )
  {
    v4 = 0;
    v5 = *(unsigned __int8 *)(a1 + 2);
    v6 = *(unsigned __int8 *)(a2[7] + 4LL);
    while ( v4 < v6 )
    {
      v7 = a2[11];
      if ( *(_BYTE *)(*(_QWORD *)(v7 + 16LL * v4) + 2LL) == (_BYTE)v5 )
      {
        v8 = *(unsigned __int8 *)(a1 + 3);
        v9 = 1;
        if ( v8 <= 1u )
          return v9 == v8;
        for ( i = v4 + 1; i < v6 && *(unsigned __int8 *)(*(_QWORD *)(v7 + 16LL * i) + 2LL) == v5 + v9; ++i )
        {
          if ( ++v9 >= v8 )
            return v9 == v8;
        }
        return 0;
      }
      ++v4;
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v11 = a2[171];
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_d(v11, (_DWORD)a2, 8, 48, (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids, v2);
  }
  return 0;
}

```

## disassembly

```asm
0x14000e994  mov     [rsp+arg_0], rbx
0x14000e999  mov     [rsp+arg_8], rsi
0x14000e99e  push    rdi
0x14000e99f  sub     rsp, 30h
0x14000e9a3  movzx   eax, byte ptr [rcx]
0x14000e9a6  mov     r8d, 8
0x14000e9ac  mov     r10, rdx
0x14000e9af  cmp     al, r8b
0x14000e9b2  jz      short loc_14000E9DB
0x14000e9b4  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000e9bb  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14000e9c2  jnz     loc_14000EA56
0x14000e9c8  xor     al, al
0x14000e9ca  mov     rbx, [rsp+38h+arg_0]
0x14000e9cf  mov     rsi, [rsp+38h+arg_8]
0x14000e9d4  add     rsp, 30h
0x14000e9d8  pop     rdi
0x14000e9d9  retn
0x14000e9db  mov     rax, [rdx+38h]
0x14000e9df  xor     r8d, r8d
0x14000e9e2  movzx   edi, byte ptr [rcx+2]
0x14000e9e6  movzx   r11d, byte ptr [rax+4]
0x14000e9eb  lea     esi, [r8+1]
0x14000e9ef  cmp     r8w, r11w
0x14000e9f3  jnb     short loc_14000E9C8
0x14000e9f5  mov     rbx, [rdx+58h]
0x14000e9f9  movzx   eax, r8w
0x14000e9fd  add     rax, rax
0x14000ea00  mov     rax, [rbx+rax*8]
0x14000ea04  cmp     [rax+2], dil
0x14000ea08  jnz     short loc_14000EA7F
0x14000ea0a  movzx   r10d, byte ptr [rcx+3]
0x14000ea0f  movzx   r9d, si
0x14000ea13  cmp     si, r10w
0x14000ea17  jnb     short loc_14000EA4A
0x14000ea19  add     r8w, si
0x14000ea1d  cmp     r8w, r11w
0x14000ea21  jnb     short loc_14000E9C8
0x14000ea23  movzx   eax, r8w
0x14000ea27  add     rax, rax
0x14000ea2a  movzx   ecx, r9w
0x14000ea2e  add     ecx, edi
0x14000ea30  mov     rax, [rbx+rax*8]
0x14000ea34  movzx   edx, byte ptr [rax+2]
0x14000ea38  cmp     edx, ecx
0x14000ea3a  jnz     short loc_14000E9C8
0x14000ea3c  add     r9w, si
0x14000ea40  add     r8w, si
0x14000ea44  cmp     r9w, r10w
0x14000ea48  jb      short loc_14000EA1D
0x14000ea4a  cmp     r9w, r10w
0x14000ea4e  setz    al
0x14000ea51  jmp     loc_14000E9CA
0x14000ea56  mov     rcx, [r10+558h]
0x14000ea5d  mov     r9d, 30h ; '0'
0x14000ea63  mov     [rsp+38h+var_10], eax
0x14000ea67  mov     dl, 2
0x14000ea69  lea     rax, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids
0x14000ea70  mov     [rsp+38h+var_18], rax
0x14000ea75  call    WPP_RECORDER_SF_d
0x14000ea7a  jmp     loc_14000E9C8
0x14000ea7f  add     r8w, si
0x14000ea83  jmp     loc_14000E9EF
```
