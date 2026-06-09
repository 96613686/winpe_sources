# ValuesArray::GetSize(ulong *)

- ea: `0x180013020`
- end: `0x18001319c`
- name: `?GetSize@ValuesArray@@UEAAJPEAK@Z`
- size: `380`
- prototype: `__int64 __fastcall(ValuesArray *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180013020`
- `0x180013880`
- `0x180014ae8`
- `0x180014bb0`
- `0x180015488`
- `0x180016010`

## string_xrefs

- `0x180013100`: `m_spJsonArray.As<IVector<IJsonValue*>> failed!`

## pseudocode

```c
__int64 __fastcall ValuesArray::GetSize(ValuesArray *this, unsigned int *a2)
{
  unsigned int ActivityIdPrefix; // eax
  int v4; // ebx
  __int64 (__fastcall ***v5)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v6)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v7; // rdx
  int v8; // eax
  int v9; // edx
  const char *v10; // rcx
  __int64 v11; // rdx
  unsigned int v13; // [rsp+48h] [rbp+10h] BYREF
  __int64 v14; // [rsp+50h] [rbp+18h] BYREF

  v14 = 0;
  v13 = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, 0);
      WPP_SF_DD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
        ActivityIdPrefix,
        -2147024809);
    }
    v4 = -2147024809;
    goto LABEL_19;
  }
  v5 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 7);
  v6 = **v5;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v14);
  v4 = v6(v5, &GUID_d44662bc_dce3_59a8_9272_4b210f33908b, &v14);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_19;
    }
    v8 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v7);
    v9 = 11;
    v10 = "m_spJsonArray.As<IVector<IJsonValue*>> failed!";
LABEL_12:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
      v8,
      (__int64)v10,
      v4);
    goto LABEL_19;
  }
  v4 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v14 + 56LL))(v14, &v13);
  if ( v4 >= 0 )
  {
    *a2 = v13;
    goto LABEL_19;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v8 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v11);
    v9 = 12;
    v10 = "spValues->get_Size failed!";
    goto LABEL_12;
  }
LABEL_19:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v14);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180013020  mov     rax, rsp
0x180013023  mov     [rax+8], rbx
0x180013027  mov     [rax+20h], rsi
0x18001302b  push    rdi
0x18001302c  sub     rsp, 30h
0x180013030  mov     qword ptr [rax+18h], 0
0x180013038  mov     rsi, rdx
0x18001303b  mov     dword ptr [rax+10h], 0
0x180013042  test    rdx, rdx
0x180013045  jnz     short loc_18001309A
0x180013047  mov     rcx, cs:WPP_GLOBAL_Control
0x18001304e  lea     rax, WPP_GLOBAL_Control
0x180013055  cmp     rcx, rax
0x180013058  jz      short loc_180013090
0x18001305a  test    byte ptr [rcx+1Ch], 8
0x18001305e  jz      short loc_180013090
0x180013060  cmp     byte ptr [rcx+19h], 2
0x180013064  jb      short loc_180013090
0x180013066  call    RdpX_GetActivityIdPrefix
0x18001306b  mov     rcx, cs:WPP_GLOBAL_Control
0x180013072  lea     edx, [rsi+0Ah]
0x180013075  mov     r9d, eax
0x180013078  mov     dword ptr [rsp+38h+var_18], 80070057h
0x180013080  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x180013087  mov     rcx, [rcx+10h]
0x18001308b  call    WPP_SF_DD
0x180013090  mov     ebx, 80070057h
0x180013095  jmp     loc_180013180
0x18001309a  mov     rdi, [rcx+38h]
0x18001309e  lea     rcx, [rsp+38h+arg_10]
0x1800130a3  mov     rax, [rdi]
0x1800130a6  mov     rbx, [rax]
0x1800130a9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x1800130ae  lea     r8, [rsp+38h+arg_10]
0x1800130b3  mov     rcx, rdi
0x1800130b6  lea     rdx, _GUID_d44662bc_dce3_59a8_9272_4b210f33908b
0x1800130bd  mov     rax, rbx
0x1800130c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130c5  mov     ebx, eax
0x1800130c7  test    eax, eax
0x1800130c9  jns     short loc_18001312C
0x1800130cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800130d2  lea     rax, WPP_GLOBAL_Control
0x1800130d9  cmp     rcx, rax
0x1800130dc  jz      loc_180013180
0x1800130e2  test    byte ptr [rcx+1Ch], 8
0x1800130e6  jz      loc_180013180
0x1800130ec  cmp     byte ptr [rcx+19h], 2
0x1800130f0  jb      loc_180013180
0x1800130f6  call    RdpX_GetActivityIdPrefix
0x1800130fb  mov     edx, 0Bh
0x180013100  lea     rcx, aMSpjsonarrayAs; "m_spJsonArray.As<IVector<IJsonValue*>> "...
0x180013107  mov     [rsp+38h+var_10], ebx
0x18001310b  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x180013112  mov     [rsp+38h+var_18], rcx
0x180013117  mov     r9d, eax
0x18001311a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013121  mov     rcx, [rcx+10h]
0x180013125  call    WPP_SF_DsD
0x18001312a  jmp     short loc_180013180
0x18001312c  mov     rcx, [rsp+38h+arg_10]
0x180013131  lea     rdx, [rsp+38h+arg_8]
0x180013136  mov     rax, [rcx]
0x180013139  mov     rax, [rax+38h]
0x18001313d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013142  mov     ebx, eax
0x180013144  test    eax, eax
0x180013146  jns     short loc_18001317A
0x180013148  mov     rcx, cs:WPP_GLOBAL_Control
0x18001314f  lea     rax, WPP_GLOBAL_Control
0x180013156  cmp     rcx, rax
0x180013159  jz      short loc_180013180
0x18001315b  test    byte ptr [rcx+1Ch], 8
0x18001315f  jz      short loc_180013180
0x180013161  cmp     byte ptr [rcx+19h], 2
0x180013165  jb      short loc_180013180
0x180013167  call    RdpX_GetActivityIdPrefix
0x18001316c  mov     edx, 0Ch
0x180013171  lea     rcx, aSpvaluesGetSiz; "spValues->get_Size failed!"
0x180013178  jmp     short loc_180013107
0x18001317a  mov     eax, [rsp+38h+arg_8]
0x18001317e  mov     [rsi], eax
0x180013180  lea     rcx, [rsp+38h+arg_10]
0x180013185  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x18001318a  mov     rsi, [rsp+38h+arg_18]
0x18001318f  mov     eax, ebx
0x180013191  mov     rbx, [rsp+38h+arg_0]
0x180013196  add     rsp, 30h
0x18001319a  pop     rdi
0x18001319b  retn
```
