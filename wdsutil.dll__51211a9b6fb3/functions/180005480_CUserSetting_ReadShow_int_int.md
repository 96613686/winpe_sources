# CUserSetting::ReadShow(int *,int)

- ea: `0x180005480`
- end: `0x1800054c4`
- name: `?ReadShow@CUserSetting@@IEAAJPEAHH@Z`
- size: `68`
- prototype: `int(CUserSetting *__hidden this, int *, int)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180005eb0`
- `0x180005ec0`
- `0x180005f20`
- `0x180005f90`

## callees

- `0x180004eb0`

## pseudocode

```c
int __fastcall CUserSetting::ReadShow(CUserSetting *this, int *a2, int a3)
{
  int result; // eax
  int v5; // r8d
  __int128 v6; // [rsp+30h] [rbp-18h] BYREF

  v6 = 0;
  result = CUserSetting::DeserializeField(this, L"Show", 4, (struct WDS_DATA *)&v6, a3);
  v5 = DWORD2(v6);
  if ( result < 0 )
    v5 = 0;
  *a2 = v5;
  return result;
}

```

## disassembly

```asm
0x180005480  push    rbx
0x180005482  sub     rsp, 40h
0x180005486  mov     rbx, rdx
0x180005489  mov     [rsp+48h+var_28], r8d; int
0x18000548e  xorps   xmm0, xmm0
0x180005491  lea     rdx, aShow; "Show"
0x180005498  mov     r8d, 4; unsigned int
0x18000549e  lea     r9, [rsp+48h+var_18]; struct WDS_DATA *
0x1800054a3  movups  [rsp+48h+var_18], xmm0
0x1800054a8  call    ?DeserializeField@CUserSetting@@IEAAJPEBGIPEAUWDS_DATA@@H@Z; CUserSetting::DeserializeField(ushort const *,uint,WDS_DATA *,int)
0x1800054ad  mov     r8d, dword ptr [rsp+48h+var_18+8]
0x1800054b2  xor     ecx, ecx
0x1800054b4  test    eax, eax
0x1800054b6  cmovs   r8d, ecx
0x1800054ba  mov     [rbx], r8d
0x1800054bd  add     rsp, 40h
0x1800054c1  pop     rbx
0x1800054c2  retn
```
