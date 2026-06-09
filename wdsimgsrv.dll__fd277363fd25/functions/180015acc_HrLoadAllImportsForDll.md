# __HrLoadAllImportsForDll

- ea: `0x180015acc`
- end: `0x180015b97`
- name: `__HrLoadAllImportsForDll`
- size: `203`
- prototype: `HRESULT __stdcall(LPCSTR szDll)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001548c`

## callees

- `0x180015acc`
- `0x180015ba0`
- `0x180015f24`
- `0x180015f58`

## string_xrefs

- `0x180015b19`: `ualapi.dll`

## pseudocode

```c
HRESULT __stdcall _HrLoadAllImportsForDll(LPCSTR szDll)
{
  __int16 *v1; // r11
  HRESULT v2; // r9d
  const ImgDelayDescr *i; // rdi
  __int64 v4; // rax
  __int64 v5; // rcx
  __int64 v6; // r10
  __int64 v7; // r8
  RVA rvaDLLName; // eax
  __int64 v9; // rcx
  char *v10; // rbx
  char *j; // rax
  char *v12; // rsi

  v1 = &_ImageBase;
  v2 = -2147024770;
  if ( *(_DWORD *)((char *)&word_1800000F4 + (int)off_18000003C) )
  {
    for ( i = (const ImgDelayDescr *)((char *)&_ImageBase
                                    + *(unsigned int *)((char *)&dword_1800000F0 + (int)off_18000003C)); ; ++i )
    {
      rvaDLLName = i->rvaDLLName;
      if ( !rvaDLLName )
        break;
      _strlen((char *)v1 + rvaDLLName);
      v4 = _strlen("ualapi.dll");
      if ( v7 == v4 && !(unsigned int)_memcmp(v5, v6) )
        break;
    }
    if ( i->rvaDLLName )
    {
      v9 = 0;
      v10 = (char *)v1 + i->rvaIAT;
      for ( j = v10; *(_QWORD *)j; v9 = (unsigned int)(v9 + 1) )
        j += 8;
      v12 = &v10[8 * v9];
      while ( v10 < v12 )
      {
        _delayLoadHelper2(i, v10);
        v10 += 8;
      }
      return 0;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180015acc  mov     [rsp+arg_0], rbx
0x180015ad1  mov     [rsp+arg_8], rsi
0x180015ad6  push    rdi
0x180015ad7  sub     rsp, 20h
0x180015adb  movsxd  rax, cs:off_18000003C
0x180015ae2  lea     r11, __ImageBase
0x180015ae9  mov     r9d, 8007007Eh
0x180015aef  cmp     dword ptr [rax+r11+0F4h], 0
0x180015af8  jz      loc_180015B83
0x180015afe  mov     edi, [rax+r11+0F0h]
0x180015b06  add     rdi, r11
0x180015b09  jmp     short loc_180015B3D
0x180015b0b  mov     r10d, eax
0x180015b0e  add     r10, r11
0x180015b11  mov     rcx, r10
0x180015b14  call    __strlen
0x180015b19  lea     rcx, aUalapiDll_0; "ualapi.dll"
0x180015b20  mov     r8, rax
0x180015b23  call    __strlen
0x180015b28  cmp     r8, rax
0x180015b2b  jnz     short loc_180015B39
0x180015b2d  mov     rdx, r10
0x180015b30  call    __memcmp
0x180015b35  test    eax, eax
0x180015b37  jz      short loc_180015B44
0x180015b39  add     rdi, 20h ; ' '
0x180015b3d  mov     eax, [rdi+4]
0x180015b40  test    eax, eax
0x180015b42  jnz     short loc_180015B0B
0x180015b44  cmp     dword ptr [rdi+4], 0
0x180015b48  jz      short loc_180015B83
0x180015b4a  mov     ebx, [rdi+0Ch]
0x180015b4d  xor     ecx, ecx
0x180015b4f  add     rbx, r11
0x180015b52  mov     rax, rbx
0x180015b55  cmp     [rbx], rcx
0x180015b58  jz      short loc_180015B66
0x180015b5a  lea     rax, [rax+8]
0x180015b5e  inc     ecx
0x180015b60  cmp     qword ptr [rax], 0
0x180015b64  jnz     short loc_180015B5A
0x180015b66  lea     rsi, [rbx+rcx*8]
0x180015b6a  jmp     short loc_180015B7B
0x180015b6c  mov     rdx, rbx
0x180015b6f  mov     rcx, rdi
0x180015b72  call    __delayLoadHelper2
0x180015b77  add     rbx, 8
0x180015b7b  cmp     rbx, rsi
0x180015b7e  jb      short loc_180015B6C
0x180015b80  xor     r9d, r9d
0x180015b83  mov     rbx, [rsp+28h+arg_0]
0x180015b88  mov     eax, r9d
0x180015b8b  mov     rsi, [rsp+28h+arg_8]
0x180015b90  add     rsp, 20h
0x180015b94  pop     rdi
0x180015b95  retn
```
