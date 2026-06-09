# Appx::Internal::GetAcquisitionInfoStringValue(Common::RegistryKey *,ushort const *,ushort *,unsigned __int64 *)

- ea: `0x1800396b0`
- end: `0x1800397d1`
- name: `?GetAcquisitionInfoStringValue@Internal@Appx@@YAJPEAVRegistryKey@Common@@PEBGPEAGPEA_K@Z`
- size: `289`
- prototype: `__int64 __fastcall(Appx::Internal *__hidden this, struct Common::RegistryKey *, LPBYTE, unsigned __int16 *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002dd0c`
- `0x180039448`

## callees

- `0x1800396b0`
- `0x1800397d8`
- `0x18004afcc`

## pseudocode

```c
__int64 __fastcall Appx::Internal::GetAcquisitionInfoStringValue(
        Appx::Internal *this,
        struct Common::RegistryKey *a2,
        LPBYTE a3,
        unsigned int *a4)
{
  int StringValue; // eax
  unsigned int v9; // r8d
  unsigned int v10; // edi
  __int64 result; // rax
  unsigned int v12; // edi
  unsigned int v13; // r8d
  unsigned int v14; // esi
  int v15; // [rsp+20h] [rbp-38h]
  int v16; // [rsp+20h] [rbp-38h]
  DWORD Type[10]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  unsigned int v19; // [rsp+60h] [rbp+8h] BYREF

  v19 = 0;
  Type[0] = 0;
  if ( !this || !a2 || !a4 || !a3 && *(_QWORD *)a4 )
    return 2147942487LL;
  StringValue = Common::RegistryKey::GetStringValue(this, (const unsigned __int16 *)a2, 0, &v19, 0, 0);
  v10 = StringValue;
  if ( StringValue >= 0 )
  {
    v12 = v19;
    if ( v19 )
    {
      if ( *(_QWORD *)a4 > (unsigned __int64)v19 && a3 )
      {
        result = Common::RegistryKey::GetStringValue(this, (const unsigned __int16 *)a2, *a4, a4, a3, Type);
        v14 = result;
        if ( (int)result >= 0 )
        {
          if ( Type[0] == 1 )
            *(_QWORD *)a4 = v12 + 1;
          else
            return 2147944029LL;
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x121, v13, (const char *)(unsigned int)result, v16);
          return v14;
        }
      }
      else
      {
        result = 2147942522LL;
        *(_QWORD *)a4 = v19 + 1;
      }
    }
    else
    {
      return 2147549183LL;
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x116, v9, (const char *)(unsigned int)StringValue, v15);
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x1800396b0  mov     rax, rsp
0x1800396b3  mov     [rax+10h], rbx
0x1800396b7  mov     [rax+18h], rbp
0x1800396bb  push    rsi
0x1800396bc  push    rdi
0x1800396bd  push    r14
0x1800396bf  sub     rsp, 40h
0x1800396c3  mov     dword ptr [rax+8], 0
0x1800396ca  mov     rbx, r9
0x1800396cd  mov     dword ptr [rax-28h], 0
0x1800396d4  mov     rsi, r8
0x1800396d7  mov     rbp, rdx
0x1800396da  mov     r14, rcx
0x1800396dd  test    rcx, rcx
0x1800396e0  jz      loc_1800397B9
0x1800396e6  test    rdx, rdx
0x1800396e9  jz      loc_1800397B9
0x1800396ef  test    rbx, rbx
0x1800396f2  jz      loc_1800397B9
0x1800396f8  test    r8, r8
0x1800396fb  jnz     short loc_180039706
0x1800396fd  cmp     [r9], r8
0x180039700  jnz     loc_1800397B9
0x180039706  mov     [rsp+58h+lpType], 0; lpType
0x18003970f  lea     r9, [rsp+58h+arg_0]; unsigned int *
0x180039714  xor     r8d, r8d; unsigned int
0x180039717  mov     [rsp+58h+var_38], 0; int
0x180039720  call    ?GetStringValue@RegistryKey@Common@@QEAAJPEBGKPEAKPEAG1@Z; Common::RegistryKey::GetStringValue(ushort const *,ulong,ulong *,ushort *,ulong *)
0x180039725  mov     edi, eax
0x180039727  test    eax, eax
0x180039729  jns     short loc_180039741
0x18003972b  mov     rcx, [rsp+58h]; this
0x180039730  mov     r9d, eax; char *
0x180039733  mov     edx, 116h; void *
0x180039738  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003973d  mov     eax, edi
0x18003973f  jmp     short loc_1800397BE
0x180039741  mov     edi, [rsp+58h+arg_0]
0x180039745  test    edi, edi
0x180039747  jnz     short loc_180039750
0x180039749  mov     eax, 8000FFFFh
0x18003974e  jmp     short loc_1800397BE
0x180039750  cmp     [rbx], rdi
0x180039753  jbe     short loc_1800397AC
0x180039755  test    rsi, rsi
0x180039758  jz      short loc_1800397AC
0x18003975a  mov     r8d, [rbx]; unsigned int
0x18003975d  lea     rax, [rsp+58h+Type]
0x180039762  mov     [rsp+58h+lpType], rax; lpType
0x180039767  mov     r9, rbx; unsigned int *
0x18003976a  mov     rdx, rbp; unsigned __int16 *
0x18003976d  mov     [rsp+58h+var_38], rsi; int
0x180039772  mov     rcx, r14; this
0x180039775  call    ?GetStringValue@RegistryKey@Common@@QEAAJPEBGKPEAKPEAG1@Z; Common::RegistryKey::GetStringValue(ushort const *,ulong,ulong *,ushort *,ulong *)
0x18003977a  mov     esi, eax
0x18003977c  test    eax, eax
0x18003977e  jns     short loc_180039796
0x180039780  mov     rcx, [rsp+58h]; this
0x180039785  mov     r9d, eax; char *
0x180039788  mov     edx, 121h; void *
0x18003978d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180039792  mov     eax, esi
0x180039794  jmp     short loc_1800397BE
0x180039796  cmp     [rsp+58h+Type], 1
0x18003979b  jz      short loc_1800397A4
0x18003979d  mov     eax, 8007065Dh
0x1800397a2  jmp     short loc_1800397BE
0x1800397a4  lea     ecx, [rdi+1]
0x1800397a7  mov     [rbx], rcx
0x1800397aa  jmp     short loc_1800397BE
0x1800397ac  lea     ecx, [rdi+1]
0x1800397af  mov     eax, 8007007Ah
0x1800397b4  mov     [rbx], rcx
0x1800397b7  jmp     short loc_1800397BE
0x1800397b9  mov     eax, 80070057h
0x1800397be  mov     rbx, [rsp+58h+arg_8]
0x1800397c3  mov     rbp, [rsp+58h+arg_10]
0x1800397c8  add     rsp, 40h
0x1800397cc  pop     r14
0x1800397ce  pop     rdi
0x1800397cf  pop     rsi
0x1800397d0  retn
```
