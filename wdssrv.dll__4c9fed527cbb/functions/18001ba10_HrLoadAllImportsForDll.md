# __HrLoadAllImportsForDll

- ea: `0x18001ba10`
- end: `0x18001bb10`
- name: `__HrLoadAllImportsForDll`
- size: `256`
- prototype: `HRESULT __stdcall(LPCSTR szDll)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001b694`

## callees

- `0x18001ba10`
- `0x18001bb20`

## string_xrefs

- `0x18001ba54`: `ualapi.dll`

## pseudocode

```c
HRESULT __stdcall _HrLoadAllImportsForDll(LPCSTR szDll)
{
  HRESULT v1; // r9d
  const ImgDelayDescr *v2; // rdi
  RVA i; // eax
  _BYTE *v4; // r8
  _BYTE *v5; // rcx
  const char *v7; // rdx
  __int64 v8; // rcx
  const char *v10; // rdx
  __int64 v11; // rcx
  char *v12; // rbx
  char *j; // rax
  char *v14; // rsi

  v1 = -2147024770;
  if ( *(_DWORD *)&byte_180000040[(int)off_18000003C + 180] )
  {
    v2 = (const ImgDelayDescr *)((char *)&_ImageBase + *(unsigned int *)&byte_180000040[(int)off_18000003C + 176]);
    for ( i = *(_DWORD *)((char *)&word_180000004 + *(unsigned int *)&byte_180000040[(int)off_18000003C + 176]); i; ++v2 )
    {
      v4 = (char *)&_ImageBase + i;
      v5 = v4;
      while ( *v5++ )
        ;
      v7 = "ualapi.dll";
      v8 = v5 - v4 - 1;
      while ( *v7++ )
        ;
      if ( v8 == v7 - "ualapi.dll" - 1 )
      {
        v10 = "ualapi.dll";
        if ( !v8 )
          break;
        while ( --v8 && *v10 == *v4 )
        {
          ++v10;
          ++v4;
        }
        if ( *(unsigned __int8 *)v10 == (unsigned __int8)*v4 )
          break;
      }
      i = v2[1].rvaDLLName;
    }
    if ( v2->rvaDLLName )
    {
      v11 = 0;
      v12 = (char *)&_ImageBase + v2->rvaIAT;
      for ( j = v12; *(_QWORD *)j; v11 = (unsigned int)(v11 + 1) )
        j += 8;
      v14 = &v12[8 * v11];
      while ( v12 < v14 )
      {
        _delayLoadHelper2(v2, v12);
        v12 += 8;
      }
      return 0;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18001ba10  mov     [rsp+arg_8], rbx
0x18001ba15  mov     [rsp+arg_10], rsi
0x18001ba1a  push    rdi
0x18001ba1b  sub     rsp, 20h
0x18001ba1f  movsxd  rax, cs:off_18000003C
0x18001ba26  lea     r10, __ImageBase
0x18001ba2d  mov     r9d, 8007007Eh
0x18001ba33  cmp     dword ptr [rax+r10+0F4h], 0
0x18001ba3c  jz      loc_18001BAFC
0x18001ba42  mov     edi, [rax+r10+0F0h]
0x18001ba4a  add     rdi, r10
0x18001ba4d  mov     eax, [rdi+4]
0x18001ba50  test    eax, eax
0x18001ba52  jz      short loc_18001BABD
0x18001ba54  lea     r11, aUalapiDll_0; "ualapi.dll"
0x18001ba5b  mov     r8d, eax
0x18001ba5e  add     r8, r10
0x18001ba61  mov     rcx, r8
0x18001ba64  mov     al, [rcx]
0x18001ba66  inc     rcx
0x18001ba69  test    al, al
0x18001ba6b  jnz     short loc_18001BA64
0x18001ba6d  sub     rcx, r8
0x18001ba70  mov     rdx, r11
0x18001ba73  dec     rcx
0x18001ba76  mov     al, [rdx]
0x18001ba78  inc     rdx
0x18001ba7b  test    al, al
0x18001ba7d  jnz     short loc_18001BA76
0x18001ba7f  sub     rdx, r11
0x18001ba82  dec     rdx
0x18001ba85  cmp     rcx, rdx
0x18001ba88  jnz     short loc_18001BAB2
0x18001ba8a  mov     rdx, r11
0x18001ba8d  test    rcx, rcx
0x18001ba90  jz      short loc_18001BABD
0x18001ba92  jmp     short loc_18001BAA1
0x18001ba94  mov     al, [r8]
0x18001ba97  cmp     [rdx], al
0x18001ba99  jnz     short loc_18001BAA7
0x18001ba9b  inc     rdx
0x18001ba9e  inc     r8
0x18001baa1  sub     rcx, 1
0x18001baa5  jnz     short loc_18001BA94
0x18001baa7  movzx   ecx, byte ptr [rdx]
0x18001baaa  movzx   eax, byte ptr [r8]
0x18001baae  cmp     ecx, eax
0x18001bab0  jz      short loc_18001BABD
0x18001bab2  mov     eax, [rdi+24h]
0x18001bab5  add     rdi, 20h ; ' '
0x18001bab9  test    eax, eax
0x18001babb  jnz     short loc_18001BA5B
0x18001babd  cmp     dword ptr [rdi+4], 0
0x18001bac1  jz      short loc_18001BAFC
0x18001bac3  mov     ebx, [rdi+0Ch]
0x18001bac6  xor     ecx, ecx
0x18001bac8  add     rbx, r10
0x18001bacb  mov     rax, rbx
0x18001bace  cmp     [rbx], rcx
0x18001bad1  jz      short loc_18001BADF
0x18001bad3  lea     rax, [rax+8]
0x18001bad7  inc     ecx
0x18001bad9  cmp     qword ptr [rax], 0
0x18001badd  jnz     short loc_18001BAD3
0x18001badf  lea     rsi, [rbx+rcx*8]
0x18001bae3  jmp     short loc_18001BAF4
0x18001bae5  mov     rdx, rbx
0x18001bae8  mov     rcx, rdi
0x18001baeb  call    __delayLoadHelper2
0x18001baf0  add     rbx, 8
0x18001baf4  cmp     rbx, rsi
0x18001baf7  jb      short loc_18001BAE5
0x18001baf9  xor     r9d, r9d
0x18001bafc  mov     rbx, [rsp+28h+arg_8]
0x18001bb01  mov     eax, r9d
0x18001bb04  mov     rsi, [rsp+28h+arg_10]
0x18001bb09  add     rsp, 20h
0x18001bb0d  pop     rdi
0x18001bb0e  retn
```
