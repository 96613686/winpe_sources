# CUInt32UserSetting::DeserializeUInt32(uint *,int)

- ea: `0x180005140`
- end: `0x180005184`
- name: `?DeserializeUInt32@CUInt32UserSetting@@IEAAJPEAIH@Z`
- size: `68`
- prototype: `int(CUInt32UserSetting *__hidden this, unsigned int *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180005840`

## callees

- `0x180004eb0`

## pseudocode

```c
int __fastcall CUInt32UserSetting::DeserializeUInt32(CUInt32UserSetting *this, unsigned int *a2, int a3)
{
  int result; // eax
  unsigned int v5; // r8d
  __int128 v6; // [rsp+30h] [rbp-18h] BYREF

  v6 = 0;
  result = CUserSetting::DeserializeField(this, L"Value", 4, (struct WDS_DATA *)&v6, a3);
  v5 = DWORD2(v6);
  if ( result < 0 )
    v5 = 0;
  *a2 = v5;
  return result;
}

```

## disassembly

```asm
0x180005140  push    rbx
0x180005142  sub     rsp, 40h
0x180005146  mov     rbx, rdx
0x180005149  mov     [rsp+48h+var_28], r8d; int
0x18000514e  xorps   xmm0, xmm0
0x180005151  lea     rdx, aValue; "Value"
0x180005158  mov     r8d, 4; unsigned int
0x18000515e  lea     r9, [rsp+48h+var_18]; struct WDS_DATA *
0x180005163  movups  [rsp+48h+var_18], xmm0
0x180005168  call    ?DeserializeField@CUserSetting@@IEAAJPEBGIPEAUWDS_DATA@@H@Z; CUserSetting::DeserializeField(ushort const *,uint,WDS_DATA *,int)
0x18000516d  mov     r8d, dword ptr [rsp+48h+var_18+8]
0x180005172  xor     ecx, ecx
0x180005174  test    eax, eax
0x180005176  cmovs   r8d, ecx
0x18000517a  mov     [rbx], r8d
0x18000517d  add     rsp, 40h
0x180005181  pop     rbx
0x180005182  retn
```
