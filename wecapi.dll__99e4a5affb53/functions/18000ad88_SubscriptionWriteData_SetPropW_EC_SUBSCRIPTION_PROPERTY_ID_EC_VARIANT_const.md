# SubscriptionWriteData::SetPropW(_EC_SUBSCRIPTION_PROPERTY_ID,_EC_VARIANT * const)

- ea: `0x18000ad88`
- end: `0x18000ae9c`
- name: `?SetPropW@SubscriptionWriteData@@QEAAKW4_EC_SUBSCRIPTION_PROPERTY_ID@@QEAU_EC_VARIANT@@@Z`
- size: `276`
- prototype: `__int64 __fastcall(SubscriptionWriteData *this, unsigned int, struct _EC_VARIANT *const)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180007aa0`

## callees

- `0x18000262c`
- `0x1800098f8`
- `0x18000a72c`
- `0x18000ad88`
- `0x18000b2b0`

## pseudocode

```c
__int64 __fastcall SubscriptionWriteData::SetPropW(
        SubscriptionWriteData *this,
        unsigned int a2,
        struct _EC_VARIANT *const a3)
{
  __int64 v4; // rdi
  DWORD Type; // ecx
  DWORD v6; // ecx
  DWORD v7; // ecx
  DWORD v8; // ecx
  DWORD v9; // ecx
  unsigned __int16 *DateTimeVal; // rax
  __int64 v11; // rbx
  unsigned __int64 v12; // rbx
  unsigned __int16 *v13; // rax

  if ( a2 < **(_DWORD **)this )
  {
    v4 = *(_QWORD *)(*(_QWORD *)this + 8LL) + 24LL * (int)a2;
    ZeroMetadataProp((struct tag_EcRpcMetadataProperty *)v4, 0);
    Type = a3->Type;
    if ( !Type )
    {
      *(_DWORD *)v4 = 0;
      return 0;
    }
    v6 = Type - 1;
    if ( !v6 )
    {
      *(_DWORD *)v4 = 1;
      *(_BYTE *)(v4 + 8) = a3->BooleanVal;
      return 0;
    }
    v7 = v6 - 1;
    if ( !v7 )
    {
      *(_DWORD *)v4 = 2;
      *(_DWORD *)(v4 + 8) = a3->BooleanVal;
      return 0;
    }
    v8 = v7 - 1;
    if ( !v8 )
    {
      *(_DWORD *)v4 = 3;
      DateTimeVal = (unsigned __int16 *)a3->DateTimeVal;
      goto LABEL_14;
    }
    v9 = v8 - 1;
    if ( !v9 )
    {
      *(_DWORD *)v4 = 4;
      *(_QWORD *)(v4 + 8) = 0;
      if ( a3->DateTimeVal )
      {
        v11 = -1;
        do
          ++v11;
        while ( *(_WORD *)(a3->DateTimeVal + 2 * v11) );
        v12 = v11 + 1;
        v13 = (unsigned __int16 *)operator new(saturated_mul(v12, 2u));
        *(_QWORD *)(v4 + 8) = v13;
        StringCchCopyW(v13, v12, a3->StringVal);
      }
      return 0;
    }
    if ( v9 == 128 )
    {
      *(_DWORD *)v4 = 4;
      DateTimeVal = ConvertStringArrayToCommaDelimitedString(a3->StringArr, a3->Count);
LABEL_14:
      *(_QWORD *)(v4 + 8) = DateTimeVal;
      return 0;
    }
  }
  return 87;
}

```

## disassembly

```asm
0x18000ad88  mov     [rsp+arg_0], rbx
0x18000ad8d  mov     [rsp+arg_8], rsi
0x18000ad92  push    rdi
0x18000ad93  sub     rsp, 20h
0x18000ad97  mov     rsi, r8
0x18000ad9a  mov     r8, [rcx]
0x18000ad9d  cmp     edx, [r8]
0x18000ada0  jnb     loc_18000AE87
0x18000ada6  movsxd  rax, edx
0x18000ada9  xor     edx, edx; bool
0x18000adab  lea     rcx, [rax+rax*2]
0x18000adaf  mov     rax, [r8+8]
0x18000adb3  lea     rdi, [rax+rcx*8]
0x18000adb7  mov     rcx, rdi; struct tag_EcRpcMetadataProperty *
0x18000adba  call    ?ZeroMetadataProp@@YAXAEAUtag_EcRpcMetadataProperty@@_N@Z; ZeroMetadataProp(tag_EcRpcMetadataProperty &,bool)
0x18000adbf  mov     ecx, [rsi+0Ch]
0x18000adc2  xor     edx, edx
0x18000adc4  test    ecx, ecx
0x18000adc6  jz      loc_18000AE81
0x18000adcc  sub     ecx, 1
0x18000adcf  jz      loc_18000AE70
0x18000add5  sub     ecx, 1
0x18000add8  jz      loc_18000AE63
0x18000adde  sub     ecx, 1
0x18000ade1  jz      short loc_18000AE54
0x18000ade3  sub     ecx, 1
0x18000ade6  jz      short loc_18000AE07
0x18000ade8  cmp     ecx, 80h
0x18000adee  jnz     loc_18000AE87
0x18000adf4  mov     dword ptr [rdi], 4
0x18000adfa  mov     edx, [rsi+8]; unsigned int
0x18000adfd  mov     rcx, [rsi]; unsigned __int16 **
0x18000ae00  call    ?ConvertStringArrayToCommaDelimitedString@@YAPEAGPEAPEAGK@Z; ConvertStringArrayToCommaDelimitedString(ushort * *,ulong)
0x18000ae05  jmp     short loc_18000AE5D
0x18000ae07  mov     dword ptr [rdi], 4
0x18000ae0d  mov     [rdi+8], rdx
0x18000ae11  mov     rax, [rsi]
0x18000ae14  test    rax, rax
0x18000ae17  jz      short loc_18000AE83
0x18000ae19  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000ae1d  mov     rbx, rcx
0x18000ae20  inc     rbx
0x18000ae23  cmp     [rax+rbx*2], dx
0x18000ae27  jnz     short loc_18000AE20
0x18000ae29  inc     rbx
0x18000ae2c  mov     eax, 2
0x18000ae31  mul     rbx
0x18000ae34  cmovb   rax, rcx
0x18000ae38  mov     rcx, rax; dwBytes
0x18000ae3b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ae40  mov     [rdi+8], rax
0x18000ae44  mov     rdx, rbx; unsigned __int64
0x18000ae47  mov     r8, [rsi]; unsigned __int16 *
0x18000ae4a  mov     rcx, rax; unsigned __int16 *
0x18000ae4d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ae52  jmp     short loc_18000AE83
0x18000ae54  mov     dword ptr [rdi], 3
0x18000ae5a  mov     rax, [rsi]
0x18000ae5d  mov     [rdi+8], rax
0x18000ae61  jmp     short loc_18000AE83
0x18000ae63  mov     dword ptr [rdi], 2
0x18000ae69  mov     eax, [rsi]
0x18000ae6b  mov     [rdi+8], eax
0x18000ae6e  jmp     short loc_18000AE83
0x18000ae70  mov     dword ptr [rdi], 1
0x18000ae76  cmp     dword ptr [rsi], 1
0x18000ae79  setz    al
0x18000ae7c  mov     [rdi+8], al
0x18000ae7f  jmp     short loc_18000AE83
0x18000ae81  mov     [rdi], edx
0x18000ae83  xor     eax, eax
0x18000ae85  jmp     short loc_18000AE8C
0x18000ae87  mov     eax, 57h ; 'W'
0x18000ae8c  mov     rbx, [rsp+28h+arg_0]
0x18000ae91  mov     rsi, [rsp+28h+arg_8]
0x18000ae96  add     rsp, 20h
0x18000ae9a  pop     rdi
0x18000ae9b  retn
```
