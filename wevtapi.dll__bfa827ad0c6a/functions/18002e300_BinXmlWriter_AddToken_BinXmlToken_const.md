# BinXmlWriter::AddToken(BinXmlToken const &)

- ea: `0x18002e300`
- end: `0x18002e4d5`
- name: `?AddToken@BinXmlWriter@@QEAAXAEBUBinXmlToken@@@Z`
- size: `469`
- prototype: `void __fastcall(BinXmlWriter *__hidden this, const struct BinXmlToken *)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x18002eebc`
- `0x18002fdb4`

## callees

- `0x180023548`
- `0x1800243e4`
- `0x18002e300`
- `0x18002e548`
- `0x18002e654`
- `0x18002e68c`
- `0x18002e6c4`
- `0x18002e900`
- `0x18002e934`
- `0x18002e9a8`
- `0x18002eb18`
- `0x18002eb60`
- `0x18002f568`
- `0x18002f61c`
- `0x18002f848`
- `0x180038fa4`

## pseudocode

```c
void __fastcall BinXmlWriter::AddToken(BinXmlWriter *this, const struct BinXmlToken *a2)
{
  int v2; // r8d
  int v3; // r8d
  int v4; // r8d
  int v5; // r8d
  int v6; // r8d
  int v7; // r8d
  bool v8; // dl
  __int64 v9; // rax
  int v10; // r8d
  int v11; // r8d
  int v12; // r8d
  int v13; // r8d
  int v14; // r8d
  int v15; // r8d
  __int64 v16; // rax
  __int64 v17; // [rsp+20h] [rbp-40h] BYREF
  __int64 v18; // [rsp+28h] [rbp-38h]
  __int128 pExceptionObject; // [rsp+30h] [rbp-30h] BYREF
  __int64 v20; // [rsp+40h] [rbp-20h]
  int v21; // [rsp+48h] [rbp-18h]
  int v22; // [rsp+4Ch] [rbp-14h]
  int v23; // [rsp+50h] [rbp-10h]

  v2 = *((_DWORD *)a2 + 4);
  if ( v2 > 7 )
  {
    v10 = v2 - 8;
    if ( v10 )
    {
      v11 = v10 - 1;
      if ( v11 )
      {
        v12 = v11 - 1;
        if ( v12 )
        {
          v13 = v12 - 1;
          if ( v13 )
          {
            v14 = v13 - 1;
            if ( !v14 )
              goto LABEL_30;
            v15 = v14 - 1;
            if ( v15 )
            {
              if ( v15 != 1 )
                goto LABEL_30;
              BinXmlWriter::WriteDependentSubstitution(this, a2, *((unsigned __int16 *)a2 + 1), *(unsigned __int16 *)a2);
            }
            else
            {
              BinXmlWriter::WriteSubstitution(this, 13, *((unsigned __int16 *)a2 + 1), *(unsigned __int16 *)a2);
            }
          }
          else
          {
            v16 = -1;
            do
              ++v16;
            while ( *(_WORD *)(*(_QWORD *)a2 + 2 * v16) );
            v17 = *(_QWORD *)a2;
            v18 = v16;
            BinXmlWriter::PIData(this, &v17);
          }
        }
        else
        {
          BinXmlWriter::PITarget(this, *(const struct BinXmlString **)a2);
        }
      }
      else
      {
        BinXmlWriter::EntityRef(this, *(const struct BinXmlString **)a2);
      }
    }
    else
    {
      BinXmlWriter::CharRef(this, *(_WORD *)a2);
    }
    return;
  }
  if ( v2 == 7 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)(*(_QWORD *)a2 + 2 * v9) );
    v17 = *(_QWORD *)a2;
    v18 = v9;
    BinXmlWriter::CDATA(this, &v17);
    return;
  }
  if ( !v2 )
  {
    BinXmlWriter::EndOfFile(this);
    return;
  }
  v3 = v2 - 1;
  if ( !v3 )
  {
    BinXmlWriter::OpenStartElementTag(this, *(const struct BinXmlString **)a2);
    return;
  }
  v4 = v3 - 1;
  if ( !v4 )
  {
    v8 = 0;
    goto LABEL_15;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    v8 = 1;
LABEL_15:
    BinXmlWriter::CloseStartElementTag(this, v8);
    return;
  }
  v6 = v5 - 1;
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( v7 )
    {
      if ( v7 == 1 )
      {
        BinXmlWriter::Attribute(this, *(const struct BinXmlString **)a2);
        return;
      }
LABEL_30:
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_69fef5147c333a0b701ade36400cc13f_Traceguids, 13);
      }
      v20 = 0;
      v21 = 13;
      v22 = -1;
      pExceptionObject = 0;
      v23 = 977;
      throw (EvtException *)&pExceptionObject;
    }
    BinXmlWriter::Value((WriteBuffer **)this, a2);
  }
  else
  {
    BinXmlWriter::EndElementTag(this);
  }
}

```

## disassembly

```asm
0x18002e300  mov     [rsp-8+arg_0], rbx
0x18002e305  push    rbp
0x18002e306  mov     rbp, rsp
0x18002e309  sub     rsp, 60h
0x18002e30d  mov     r8d, [rdx+10h]
0x18002e311  xor     ebx, ebx
0x18002e313  cmp     r8d, 7
0x18002e317  jg      loc_18002E3BB
0x18002e31d  jz      short loc_18002E394
0x18002e31f  test    r8d, r8d
0x18002e322  jz      short loc_18002E38A
0x18002e324  sub     r8d, 1
0x18002e328  jz      short loc_18002E37D
0x18002e32a  sub     r8d, 1
0x18002e32e  jz      short loc_18002E371
0x18002e330  sub     r8d, 1
0x18002e334  jz      short loc_18002E36D
0x18002e336  sub     r8d, 1
0x18002e33a  jz      short loc_18002E363
0x18002e33c  sub     r8d, 1
0x18002e340  jz      short loc_18002E359
0x18002e342  cmp     r8d, 1
0x18002e346  jnz     loc_18002E420
0x18002e34c  mov     rdx, [rdx]; struct BinXmlString *
0x18002e34f  call    ?Attribute@BinXmlWriter@@QEAAXAEBVBinXmlString@@@Z; BinXmlWriter::Attribute(BinXmlString const &)
0x18002e354  jmp     loc_18002E4CA
0x18002e359  call    ?Value@BinXmlWriter@@QEAAXAEBUBinXmlVariant@@@Z; BinXmlWriter::Value(BinXmlVariant const &)
0x18002e35e  jmp     loc_18002E4CA
0x18002e363  call    ?EndElementTag@BinXmlWriter@@QEAAXXZ; BinXmlWriter::EndElementTag(void)
0x18002e368  jmp     loc_18002E4CA
0x18002e36d  mov     dl, 1
0x18002e36f  jmp     short loc_18002E373
0x18002e371  xor     edx, edx; bool
0x18002e373  call    ?CloseStartElementTag@BinXmlWriter@@QEAAX_N@Z; BinXmlWriter::CloseStartElementTag(bool)
0x18002e378  jmp     loc_18002E4CA
0x18002e37d  mov     rdx, [rdx]; struct BinXmlString *
0x18002e380  call    ?OpenStartElementTag@BinXmlWriter@@QEAAXAEBVBinXmlString@@@Z; BinXmlWriter::OpenStartElementTag(BinXmlString const &)
0x18002e385  jmp     loc_18002E4CA
0x18002e38a  call    ?EndOfFile@BinXmlWriter@@QEAAXXZ; BinXmlWriter::EndOfFile(void)
0x18002e38f  jmp     loc_18002E4CA
0x18002e394  mov     r8, [rdx]
0x18002e397  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002e39b  inc     rax
0x18002e39e  cmp     [r8+rax*2], bx
0x18002e3a3  jnz     short loc_18002E39B
0x18002e3a5  lea     rdx, [rbp+var_40]
0x18002e3a9  mov     [rbp+var_40], r8
0x18002e3ad  mov     [rbp+var_38], rax
0x18002e3b1  call    ?CDATA@BinXmlWriter@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; BinXmlWriter::CDATA(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18002e3b6  jmp     loc_18002E4CA
0x18002e3bb  sub     r8d, 8
0x18002e3bf  jz      loc_18002E4C2
0x18002e3c5  sub     r8d, 1
0x18002e3c9  jz      loc_18002E4B8
0x18002e3cf  sub     r8d, 1
0x18002e3d3  jz      loc_18002E4AE
0x18002e3d9  sub     r8d, 1
0x18002e3dd  jz      loc_18002E48A
0x18002e3e3  sub     r8d, 1
0x18002e3e7  jz      short loc_18002E420
0x18002e3e9  sub     r8d, 1
0x18002e3ed  jz      short loc_18002E408
0x18002e3ef  cmp     r8d, 1
0x18002e3f3  jnz     short loc_18002E420
0x18002e3f5  movzx   r8d, word ptr [rdx+2]
0x18002e3fa  movzx   r9d, word ptr [rdx]
0x18002e3fe  call    ?WriteDependentSubstitution@BinXmlWriter@@AEAAXW4BinXmlTokType@@W4BinXmlVarType@@G@Z; BinXmlWriter::WriteDependentSubstitution(BinXmlTokType,BinXmlVarType,ushort)
0x18002e403  jmp     loc_18002E4CA
0x18002e408  movzx   r8d, word ptr [rdx+2]
0x18002e40d  movzx   r9d, word ptr [rdx]
0x18002e411  mov     edx, 0Dh
0x18002e416  call    ?WriteSubstitution@BinXmlWriter@@AEAAXW4BinXmlTokType@@W4BinXmlVarType@@G@Z; BinXmlWriter::WriteSubstitution(BinXmlTokType,BinXmlVarType,ushort)
0x18002e41b  jmp     loc_18002E4CA
0x18002e420  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e427  lea     rax, WPP_GLOBAL_Control
0x18002e42e  cmp     rcx, rax
0x18002e431  jz      short loc_18002E458
0x18002e433  test    byte ptr [rcx+1Ch], 2
0x18002e437  jz      short loc_18002E458
0x18002e439  cmp     byte ptr [rcx+19h], 2
0x18002e43d  jb      short loc_18002E458
0x18002e43f  mov     rcx, [rcx+10h]
0x18002e443  lea     r8, WPP_69fef5147c333a0b701ade36400cc13f_Traceguids
0x18002e44a  mov     edx, 16h
0x18002e44f  lea     r9d, [rdx-9]
0x18002e453  call    WPP_SF_D
0x18002e458  xorps   xmm0, xmm0
0x18002e45b  mov     [rbp+var_20], rbx
0x18002e45f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18002e466  mov     [rbp+var_18], 0Dh
0x18002e46d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18002e471  mov     [rbp+var_14], 0FFFFFFFFh
0x18002e478  movdqu  [rbp+pExceptionObject], xmm0
0x18002e47d  mov     [rbp+var_10], 3D1h
0x18002e484  call    _CxxThrowException_0
0x18002e48a  mov     r8, [rdx]
0x18002e48d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002e491  inc     rax
0x18002e494  cmp     [r8+rax*2], bx
0x18002e499  jnz     short loc_18002E491
0x18002e49b  lea     rdx, [rbp+var_40]
0x18002e49f  mov     [rbp+var_40], r8
0x18002e4a3  mov     [rbp+var_38], rax
0x18002e4a7  call    ?PIData@BinXmlWriter@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; BinXmlWriter::PIData(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18002e4ac  jmp     short loc_18002E4CA
0x18002e4ae  mov     rdx, [rdx]; struct BinXmlString *
0x18002e4b1  call    ?PITarget@BinXmlWriter@@QEAAXAEBVBinXmlString@@@Z; BinXmlWriter::PITarget(BinXmlString const &)
0x18002e4b6  jmp     short loc_18002E4CA
0x18002e4b8  mov     rdx, [rdx]; struct BinXmlString *
0x18002e4bb  call    ?EntityRef@BinXmlWriter@@QEAAXAEBVBinXmlString@@@Z; BinXmlWriter::EntityRef(BinXmlString const &)
0x18002e4c0  jmp     short loc_18002E4CA
0x18002e4c2  movzx   edx, word ptr [rdx]; wchar_t
0x18002e4c5  call    ?CharRef@BinXmlWriter@@QEAAX_W@Z; BinXmlWriter::CharRef(wchar_t)
0x18002e4ca  mov     rbx, [rsp+60h+arg_0]
0x18002e4cf  add     rsp, 60h
0x18002e4d3  pop     rbp
0x18002e4d4  retn
```
