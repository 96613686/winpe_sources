# _attribute_t::Copy(tagHELPER_ATTRIBUTE const *)

- ea: `0x180004330`
- end: `0x180004458`
- name: `?Copy@_attribute_t@@QEAAJPEBUtagHELPER_ATTRIBUTE@@@Z`
- size: `296`
- prototype: `__int64 __fastcall(_attribute_t *__hidden this, const struct tagHELPER_ATTRIBUTE *)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180005b30`
- `0x180011ef0`
- `0x180012350`
- `0x180012940`

## callees

- `0x180004330`
- `0x180004ac4`
- `0x18000c6cc`
- `0x18000c764`
- `0x18000ca0c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004403`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004403`

## pseudocode

```c
__int64 __fastcall _attribute_t::Copy(struct tagHELPER_ATTRIBUTE *this, const struct tagHELPER_ATTRIBUTE *a2)
{
  ATTRIBUTE_TYPE type; // esi
  __int64 v6; // rbp
  char *p_Char; // r14
  __int64 v8; // rcx
  char *v9; // rax
  int v10; // eax
  int v11; // esi
  const unsigned __int16 *pwszName; // rdi

  if ( !a2 )
    return 2147942487LL;
  if ( this == a2 )
    return 0;
  type = a2->type;
  _attribute_t::FreeAll((LPVOID *)&this->pwszName);
  v6 = 128;
  p_Char = &this->Char;
  v8 = 128;
  v9 = &this->Char;
  do
  {
    *v9++ = 0;
    --v8;
  }
  while ( v8 );
  if ( type == AT_STRING )
  {
    v10 = _attribute_t::SetValue((LPVOID *)&this->pwszName, a2->PWStr);
  }
  else
  {
    if ( type != AT_OCTET_STRING )
    {
      *(_OWORD *)&this->pwszName = *(_OWORD *)&a2->pwszName;
      *(_OWORD *)&this->Boolean = *(_OWORD *)&a2->Boolean;
      *((_OWORD *)&this->OctetString + 1) = *((_OWORD *)&a2->OctetString + 1);
      *((_OWORD *)&this->OctetString + 2) = *((_OWORD *)&a2->OctetString + 2);
      *((_OWORD *)&this->OctetString + 3) = *((_OWORD *)&a2->OctetString + 3);
      *((_OWORD *)&this->OctetString + 4) = *((_OWORD *)&a2->OctetString + 4);
      *((_OWORD *)&this->OctetString + 5) = *((_OWORD *)&a2->OctetString + 5);
      *((_OWORD *)&this->OctetString + 6) = *((_OWORD *)&a2->OctetString + 6);
      *((_OWORD *)&this->OctetString + 7) = *((_OWORD *)&a2->OctetString + 7);
LABEL_13:
      this->pwszName = 0;
      pwszName = a2->pwszName;
      CoTaskMemFree(0);
      this->pwszName = 0;
      if ( pwszName )
      {
        v11 = StringCchCopyWithAlloc(&this->pwszName, 0xFFFF, pwszName);
        if ( v11 < 0 )
          goto LABEL_15;
      }
      return 0;
    }
    v10 = _attribute_t::SetValue((LPVOID *)&this->pwszName, &a2->OctetString);
  }
  v11 = v10;
  if ( v10 >= 0 )
    goto LABEL_13;
LABEL_15:
  _attribute_t::FreeAll((LPVOID *)&this->pwszName);
  do
  {
    *p_Char++ = 0;
    --v6;
  }
  while ( v6 );
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180004330  push    rbx
0x180004332  push    rbp
0x180004333  push    rsi
0x180004334  push    rdi
0x180004335  push    r14
0x180004337  sub     rsp, 20h
0x18000433b  mov     rdi, rdx
0x18000433e  mov     rbx, rcx
0x180004341  test    rdx, rdx
0x180004344  jnz     short loc_180004350
0x180004346  mov     eax, 80070057h
0x18000434b  jmp     loc_18000444C
0x180004350  cmp     rbx, rdi
0x180004353  jz      loc_18000444A
0x180004359  mov     esi, [rdx+8]
0x18000435c  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x180004361  mov     ebp, 80h
0x180004366  lea     r14, [rbx+10h]
0x18000436a  mov     ecx, ebp
0x18000436c  mov     rax, r14
0x18000436f  mov     byte ptr [rax], 0
0x180004372  inc     rax
0x180004375  sub     rcx, 1
0x180004379  jnz     short loc_18000436F
0x18000437b  cmp     esi, 0Ah
0x18000437e  jnz     short loc_18000438E
0x180004380  mov     rdx, [rdi+10h]; unsigned __int16 *
0x180004384  mov     rcx, rbx; this
0x180004387  call    ?SetValue@_attribute_t@@QEAAJPEBG@Z; _attribute_t::SetValue(ushort const *)
0x18000438c  jmp     short loc_18000439F
0x18000438e  cmp     esi, 0Eh
0x180004391  jnz     short loc_1800043AB
0x180004393  lea     rdx, [rdi+10h]; struct tagOCTET_STRING *
0x180004397  mov     rcx, rbx; this
0x18000439a  call    ?SetValue@_attribute_t@@QEAAJPEBUtagOCTET_STRING@@@Z; _attribute_t::SetValue(tagOCTET_STRING const *)
0x18000439f  mov     esi, eax
0x1800043a1  test    eax, eax
0x1800043a3  js      loc_180004431
0x1800043a9  jmp     short loc_1800043F7
0x1800043ab  movups  xmm0, xmmword ptr [rdi]
0x1800043ae  movups  xmmword ptr [rbx], xmm0
0x1800043b1  movups  xmm1, xmmword ptr [rdi+10h]
0x1800043b5  movups  xmmword ptr [rbx+10h], xmm1
0x1800043b9  movups  xmm0, xmmword ptr [rdi+20h]
0x1800043bd  movups  xmmword ptr [rbx+20h], xmm0
0x1800043c1  movups  xmm1, xmmword ptr [rdi+30h]
0x1800043c5  movups  xmmword ptr [rbx+30h], xmm1
0x1800043c9  movups  xmm0, xmmword ptr [rdi+40h]
0x1800043cd  movups  xmmword ptr [rbx+40h], xmm0
0x1800043d1  movups  xmm1, xmmword ptr [rdi+50h]
0x1800043d5  movups  xmmword ptr [rbx+50h], xmm1
0x1800043d9  movups  xmm0, xmmword ptr [rdi+60h]
0x1800043dd  movups  xmmword ptr [rbx+60h], xmm0
0x1800043e1  movups  xmm1, xmmword ptr [rdi+70h]
0x1800043e5  movups  xmmword ptr [rbx+70h], xmm1
0x1800043e9  movups  xmm0, xmmword ptr [rdi+80h]
0x1800043f0  movups  xmmword ptr [rbx+80h], xmm0
0x1800043f7  mov     qword ptr [rbx], 0
0x1800043fe  xor     ecx, ecx; pv
0x180004400  mov     rdi, [rdi]
0x180004403  call    cs:__imp_CoTaskMemFree
0x18000440a  nop     dword ptr [rax+rax+00h]
0x18000440f  mov     qword ptr [rbx], 0
0x180004416  test    rdi, rdi
0x180004419  jz      short loc_18000444A
0x18000441b  mov     r8, rdi; unsigned __int16 *
0x18000441e  mov     edx, 0FFFFh; unsigned __int64
0x180004423  mov     rcx, rbx; unsigned __int16 **
0x180004426  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x18000442b  mov     esi, eax
0x18000442d  test    eax, eax
0x18000442f  jns     short loc_18000444A
0x180004431  mov     rcx, rbx; this
0x180004434  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x180004439  mov     byte ptr [r14], 0
0x18000443d  inc     r14
0x180004440  sub     rbp, 1
0x180004444  jnz     short loc_180004439
0x180004446  mov     eax, esi
0x180004448  jmp     short loc_18000444C
0x18000444a  xor     eax, eax
0x18000444c  add     rsp, 20h
0x180004450  pop     r14
0x180004452  pop     rdi
0x180004453  pop     rsi
0x180004454  pop     rbp
0x180004455  pop     rbx
0x180004456  retn
```
