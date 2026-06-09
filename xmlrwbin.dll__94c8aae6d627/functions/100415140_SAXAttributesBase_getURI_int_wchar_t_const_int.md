# SAXAttributesBase::getURI(int,wchar_t const * *,int *)

- ea: `0x100415140`
- end: `0x1004151a0`
- name: `?getURI@SAXAttributesBase@@UEAAJHPEAPEB_WPEAH@Z`
- size: `96`
- prototype: `__int64 __fastcall(SAXAttributesBase *__hidden this, int, const wchar_t **, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x100401350`
- `0x100415140`

## pseudocode

```c
__int64 __fastcall SAXAttributesBase::getURI(SAXAttributesBase *this, int a2, const wchar_t **a3, int *a4)
{
  __int64 v4; // rdx
  __int64 result; // rax

  if ( a2 < 0 || a2 >= *((_DWORD *)this + 10) )
    return 2147942487LL;
  v4 = *((_QWORD *)this + 4) + 32LL * (unsigned int)(5 * a2);
  if ( v4 )
  {
    if ( *(_DWORD *)v4 != 17 )
    {
      MXRRaiseException(-2147467259);
      JUMPOUT(0x10041519FLL);
    }
    *a3 = *(const wchar_t **)(v4 + 8);
    *a4 = *(_DWORD *)(v4 + 16) >> 1;
    return 0;
  }
  else
  {
    result = 0;
    *a3 = 0;
    *a4 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x100415140  sub     rsp, 28h
0x100415144  xor     r10d, r10d
0x100415147  test    edx, edx
0x100415149  js      short loc_100415187
0x10041514b  cmp     edx, [rcx+28h]
0x10041514e  jge     short loc_100415187
0x100415150  lea     edx, [rdx+rdx*4]
0x100415153  shl     rdx, 5
0x100415157  add     rdx, [rcx+20h]
0x10041515b  jz      short loc_100415179
0x10041515d  cmp     dword ptr [rdx], 11h
0x100415160  jnz     short loc_100415195
0x100415162  mov     rax, [rdx+8]
0x100415166  mov     [r8], rax
0x100415169  mov     eax, [rdx+10h]
0x10041516c  shr     eax, 1
0x10041516e  mov     [r9], eax
0x100415171  mov     eax, r10d
0x100415174  add     rsp, 28h
0x100415178  retn
0x100415179  mov     eax, r10d
0x10041517c  mov     [r8], r10
0x10041517f  mov     [r9], eax
0x100415182  add     rsp, 28h
0x100415186  retn
0x100415187  mov     r10d, 80070057h
0x10041518d  mov     eax, r10d
0x100415190  add     rsp, 28h
0x100415194  retn
0x100415195  mov     ecx, 80004005h; int
0x10041519a  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
