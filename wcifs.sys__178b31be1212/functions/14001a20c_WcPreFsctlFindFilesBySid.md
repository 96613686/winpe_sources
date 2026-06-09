# WcPreFsctlFindFilesBySid

- ea: `0x14001a20c`
- end: `0x14001a35b`
- name: `WcPreFsctlFindFilesBySid`
- size: `335`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1400231a0`

## callees

- `0x140001008`
- `0x140001030`
- `0x1400016b4`
- `0x140001c44`
- `0x140007c60`
- `0x14001a20c`

## pseudocode

```c
__int64 __fastcall WcPreFsctlFindFilesBySid(__int64 a1, __int64 a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rsi
  int v5; // edx
  __int64 v6; // rcx
  char v8; // [rsp+40h] [rbp-68h] BYREF
  __int64 v9; // [rsp+48h] [rbp-60h] BYREF
  _BYTE v10[32]; // [rsp+50h] [rbp-58h] BYREF
  char *v11; // [rsp+70h] [rbp-38h]
  __int64 v12; // [rsp+78h] [rbp-30h]
  __int64 *v13; // [rsp+80h] [rbp-28h]
  __int64 v14; // [rsp+88h] [rbp-20h]

  v3 = 1;
  v4 = *(unsigned int *)(*(_QWORD *)(a1 + 16) + 40LL);
  if ( (unsigned __int8)WcUnionExistsForFileObject(a1, *(_QWORD *)(a2 + 24), *(_QWORD *)(a2 + 32)) )
  {
    if ( (unsigned int)dword_14000E060 > 5 && (unsigned __int8)tlgKeywordOn(&dword_14000E060, 0x400000000000LL) )
    {
      v8 = 3;
      v11 = &v8;
      v12 = 1;
      v13 = &v9;
      v9 = v4;
      v14 = 8;
      tlgWriteTransfer_EtwWriteTransfer(v6, qword_14000B798, 0, 0, 4, v10);
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 3;
      WPP_RECORDER_SF_sDD(
        wil_details_featureDescriptors_a->DeviceExtension,
        v5,
        7,
        17,
        (__int64)WPP_c070de6cd2643f4183d5a0f659a39519_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\fsctrl.c",
        116,
        v4);
    }
    *(_DWORD *)(a1 + 24) = -1073741637;
    v3 = 4;
    *(_QWORD *)(a1 + 32) = 0;
  }
  return v3;
}

```

## disassembly

```asm
0x14001a20c  mov     [rsp+arg_10], rbx
0x14001a211  mov     [rsp+arg_18], rsi
0x14001a216  push    rdi
0x14001a217  sub     rsp, 0A0h
0x14001a21e  mov     rax, cs:__security_cookie
0x14001a225  xor     rax, rsp
0x14001a228  mov     [rsp+0A8h+var_18], rax
0x14001a230  mov     rax, [rcx+10h]
0x14001a234  mov     rdi, rcx
0x14001a237  mov     r8, [rdx+20h]
0x14001a23b  mov     ebx, 1
0x14001a240  mov     rdx, [rdx+18h]
0x14001a244  mov     esi, [rax+28h]
0x14001a247  call    WcUnionExistsForFileObject
0x14001a24c  test    al, al
0x14001a24e  jz      loc_14001A333
0x14001a254  mov     eax, cs:dword_14000E060
0x14001a25a  cmp     eax, 5
0x14001a25d  jbe     short loc_14001A2CF
0x14001a25f  mov     rdx, 400000000000h
0x14001a269  lea     rcx, dword_14000E060
0x14001a270  call    _tlgKeywordOn
0x14001a275  test    al, al
0x14001a277  jz      short loc_14001A2CF
0x14001a279  lea     rax, [rsp+0A8h+var_68]
0x14001a27e  mov     [rsp+0A8h+var_68], 3
0x14001a283  mov     [rsp+0A8h+var_38], rax
0x14001a288  lea     rdx, qword_14000B798
0x14001a28f  lea     rax, [rsp+0A8h+var_60]
0x14001a294  mov     [rsp+0A8h+var_30], rbx
0x14001a299  mov     [rsp+0A8h+var_28], rax
0x14001a2a1  xor     r9d, r9d
0x14001a2a4  lea     rax, [rsp+0A8h+var_58]
0x14001a2a9  mov     [rsp+0A8h+var_60], rsi
0x14001a2ae  mov     [rsp+0A8h+var_80], rax
0x14001a2b3  xor     r8d, r8d
0x14001a2b6  mov     dword ptr [rsp+0A8h+var_88], 4
0x14001a2be  mov     [rsp+0A8h+var_20], 8
0x14001a2ca  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001a2cf  lea     rax, WPP_RECORDER_INITIALIZED
0x14001a2d6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001a2dd  jz      short loc_14001A31F
0x14001a2df  mov     rcx, cs:wil_details_featureDescriptors_a
0x14001a2e6  lea     rax, aOnecoreBaseFsW_2; "onecore\\base\\fs\\wci\\wcifs\\fsctrl.c"
0x14001a2ed  mov     [rsp+0A8h+var_70], esi
0x14001a2f1  mov     r9d, 11h
0x14001a2f7  mov     [rsp+0A8h+var_78], 274h
0x14001a2ff  mov     dl, 3
0x14001a301  mov     [rsp+0A8h+var_80], rax
0x14001a306  lea     rax, WPP_c070de6cd2643f4183d5a0f659a39519_Traceguids
0x14001a30d  mov     rcx, [rcx+40h]
0x14001a311  lea     r8d, [r9-0Ah]
0x14001a315  mov     [rsp+0A8h+var_88], rax
0x14001a31a  call    WPP_RECORDER_SF_sDD
0x14001a31f  mov     dword ptr [rdi+18h], 0C00000BBh
0x14001a326  mov     ebx, 4
0x14001a32b  mov     qword ptr [rdi+20h], 0
0x14001a333  mov     eax, ebx
0x14001a335  mov     rcx, [rsp+0A8h+var_18]
0x14001a33d  xor     rcx, rsp; StackCookie
0x14001a340  call    __security_check_cookie
0x14001a345  lea     r11, [rsp+0A8h+var_8]
0x14001a34d  mov     rbx, [r11+20h]
0x14001a351  mov     rsi, [r11+28h]
0x14001a355  mov     rsp, r11
0x14001a358  pop     rdi
0x14001a359  retn
```
