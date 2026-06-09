# CUInt64UserSetting::DeserializeUInt64(unsigned __int64 *,int)

- ea: `0x180005190`
- end: `0x1800051d4`
- name: `?DeserializeUInt64@CUInt64UserSetting@@IEAAJPEA_KH@Z`
- size: `68`
- prototype: `int(CUInt64UserSetting *__hidden this, unsigned __int64 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800058e0`

## callees

- `0x180004eb0`

## pseudocode

```c
int __fastcall CUInt64UserSetting::DeserializeUInt64(CUInt64UserSetting *this, unsigned __int64 *a2, int a3)
{
  int result; // eax
  unsigned __int64 v5; // r8
  __int128 v6; // [rsp+30h] [rbp-18h] BYREF

  v6 = 0;
  result = CUserSetting::DeserializeField(this, L"Value", 5, (struct WDS_DATA *)&v6, a3);
  v5 = *((_QWORD *)&v6 + 1);
  if ( result < 0 )
    v5 = 0;
  *a2 = v5;
  return result;
}

```

## disassembly

```asm
0x180005190  push    rbx
0x180005192  sub     rsp, 40h
0x180005196  mov     rbx, rdx
0x180005199  mov     [rsp+48h+var_28], r8d; int
0x18000519e  xorps   xmm0, xmm0
0x1800051a1  lea     rdx, aValue; "Value"
0x1800051a8  mov     r8d, 5; unsigned int
0x1800051ae  lea     r9, [rsp+48h+var_18]; struct WDS_DATA *
0x1800051b3  movups  [rsp+48h+var_18], xmm0
0x1800051b8  call    ?DeserializeField@CUserSetting@@IEAAJPEBGIPEAUWDS_DATA@@H@Z; CUserSetting::DeserializeField(ushort const *,uint,WDS_DATA *,int)
0x1800051bd  mov     r8, qword ptr [rsp+48h+var_18+8]
0x1800051c2  xor     ecx, ecx
0x1800051c4  test    eax, eax
0x1800051c6  cmovs   r8, rcx
0x1800051ca  mov     [rbx], r8
0x1800051cd  add     rsp, 40h
0x1800051d1  pop     rbx
0x1800051d2  retn
```
