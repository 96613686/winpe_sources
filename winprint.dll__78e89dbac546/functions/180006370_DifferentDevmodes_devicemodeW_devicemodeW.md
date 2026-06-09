# DifferentDevmodes(_devicemodeW *,_devicemodeW *)

- ea: `0x180006370`
- end: `0x180006467`
- name: `?DifferentDevmodes@@YAHPEAU_devicemodeW@@0@Z`
- size: `247`
- prototype: `__int64 __fastcall(struct _devicemodeW *, struct _devicemodeW *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180003200`

## callees

- `0x180006370`
- `0x1800077a9`

## pseudocode

```c
_BOOL8 __fastcall DifferentDevmodes(struct _devicemodeW *a1, struct _devicemodeW *a2)
{
  unsigned int v5; // esi
  struct _devicemodeW *v6; // rax
  int v7; // r8d
  int v8; // edx
  WCHAR *dmFormName; // rax
  int v10; // r8d
  int v11; // ecx

  if ( a1 == a2 )
    return 0;
  if ( !a1 )
    return 1;
  if ( !a2 )
    return 1;
  v5 = a1->dmSize + a1->dmDriverExtra;
  if ( v5 != a2->dmSize + a2->dmDriverExtra )
    return 1;
  v6 = a1;
  do
  {
    v7 = *(unsigned __int16 *)((char *)v6->dmDeviceName + (char *)a2 - (char *)a1);
    v8 = v6->dmDeviceName[0] - v7;
    if ( v8 )
      break;
    v6 = (struct _devicemodeW *)((char *)v6 + 2);
  }
  while ( v7 );
  if ( v8 || v5 < 0xA6 || memcmp_0(&a1->dmSpecVersion, &a2->dmSpecVersion, 0x22u) || a1->dmCollate != a2->dmCollate )
    return 1;
  dmFormName = a1->dmFormName;
  do
  {
    v10 = *(WCHAR *)((char *)dmFormName + (char *)a2 - (char *)a1);
    v11 = *dmFormName - v10;
    if ( v11 )
      break;
    ++dmFormName;
  }
  while ( v10 );
  return v11 || memcmp_0(&a1->dmLogPixels, &a2->dmLogPixels, v5 - 166);
}

```

## disassembly

```asm
0x180006370  mov     [rsp+arg_0], rbx
0x180006375  mov     [rsp+arg_8], rsi
0x18000637a  push    rdi
0x18000637b  sub     rsp, 20h
0x18000637f  mov     rbx, rdx
0x180006382  mov     rdi, rcx
0x180006385  cmp     rcx, rdx
0x180006388  jnz     short loc_180006391
0x18000638a  xor     eax, eax
0x18000638c  jmp     loc_180006457
0x180006391  test    rdi, rdi
0x180006394  jz      loc_180006452
0x18000639a  test    rbx, rbx
0x18000639d  jz      loc_180006452
0x1800063a3  movzx   eax, word ptr [rcx+44h]
0x1800063a7  movzx   esi, word ptr [rcx+46h]
0x1800063ab  movzx   ecx, word ptr [rdx+46h]
0x1800063af  add     esi, eax
0x1800063b1  movzx   eax, word ptr [rdx+44h]
0x1800063b5  add     ecx, eax
0x1800063b7  cmp     esi, ecx
0x1800063b9  jnz     loc_180006452
0x1800063bf  mov     rcx, rbx
0x1800063c2  mov     rax, rdi
0x1800063c5  sub     rcx, rdi
0x1800063c8  movzx   edx, word ptr [rax]
0x1800063cb  movzx   r8d, word ptr [rax+rcx]
0x1800063d0  sub     edx, r8d
0x1800063d3  jnz     short loc_1800063DE
0x1800063d5  add     rax, 2
0x1800063d9  test    r8d, r8d
0x1800063dc  jnz     short loc_1800063C8
0x1800063de  test    edx, edx
0x1800063e0  jnz     short loc_180006452
0x1800063e2  cmp     esi, 0A6h
0x1800063e8  jb      short loc_180006452
0x1800063ea  lea     rdx, [rbx+40h]; Buf2
0x1800063ee  mov     r8d, 22h ; '"'; Size
0x1800063f4  lea     rcx, [rdi+40h]; Buf1
0x1800063f8  call    memcmp_0
0x1800063fd  test    eax, eax
0x1800063ff  jnz     short loc_180006452
0x180006401  movzx   eax, word ptr [rbx+64h]
0x180006405  cmp     [rdi+64h], ax
0x180006409  jnz     short loc_180006452
0x18000640b  lea     rdx, [rbx+66h]
0x18000640f  lea     rax, [rdi+66h]
0x180006413  sub     rdx, rax
0x180006416  movzx   ecx, word ptr [rax]
0x180006419  movzx   r8d, word ptr [rax+rdx]
0x18000641e  sub     ecx, r8d
0x180006421  jnz     short loc_18000642C
0x180006423  add     rax, 2
0x180006427  test    r8d, r8d
0x18000642a  jnz     short loc_180006416
0x18000642c  test    ecx, ecx
0x18000642e  jnz     short loc_180006452
0x180006430  lea     r8d, [rsi-0A6h]; Size
0x180006437  lea     rdx, [rbx+0A6h]; Buf2
0x18000643e  lea     rcx, [rdi+0A6h]; Buf1
0x180006445  call    memcmp_0
0x18000644a  test    eax, eax
0x18000644c  jz      loc_18000638A
0x180006452  mov     eax, 1
0x180006457  mov     rbx, [rsp+28h+arg_0]
0x18000645c  mov     rsi, [rsp+28h+arg_8]
0x180006461  add     rsp, 20h
0x180006465  pop     rdi
0x180006466  retn
```
