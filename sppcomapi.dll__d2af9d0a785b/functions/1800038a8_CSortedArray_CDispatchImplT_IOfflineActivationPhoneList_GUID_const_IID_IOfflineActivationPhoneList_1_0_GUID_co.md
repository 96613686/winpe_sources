# CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::Find(ulong,int *)

- ea: `0x1800038a8`
- end: `0x180003947`
- name: `?Find@?$CSortedArray@UCTypeInfoItem@?$CDispatchImplT@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEBA_NKPEAH@Z`
- size: `159`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180003020`
- `0x1800050f0`
- `0x18001c300`
- `0x18001c470`
- `0x18001c5e0`
- `0x18001c750`
- `0x18001c8c0`
- `0x18001f5f0`
- `0x18001f760`

## callees

- `0x1800038a8`

## pseudocode

```c
char __fastcall CSortedArray<CDispatchImplT<IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,unsigned long,CAdaptorDefault,CPoliciesDefault>::Find(
        __int64 a1,
        unsigned int a2,
        int *a3)
{
  int v3; // r11d
  __int64 v4; // rbp
  int v5; // r9d
  unsigned int v6; // r10d
  signed int v7; // esi
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  char result; // al

  v3 = *(_DWORD *)(a1 + 4);
  v4 = *(_QWORD *)(a1 + 8);
  if ( v3 )
  {
    v5 = 0;
    v6 = *(_DWORD *)(a1 + 4);
    if ( v3 <= 0 )
      goto LABEL_10;
    do
    {
      v7 = (v6 >> 1) + v5;
      v8 = *(_DWORD *)(v4 + 16LL * v7 + 8);
      if ( (((__PAIR64__(a2 < v8, v8) - a2) >> 32) & 0x80000000) == 0LL )
      {
        v6 >>= 1;
      }
      else
      {
        v5 = v7 + 1;
        v6 += -1 - (v6 >> 1);
      }
    }
    while ( (int)v6 > 0 );
    if ( v5 >= v3
      || (v9 = *(_DWORD *)(v4 + 16LL * v5 + 8), (((__PAIR64__(v9 < a2, a2) - v9) >> 32) & 0x80000000) != 0LL) )
    {
LABEL_10:
      result = 0;
    }
    else
    {
      result = 1;
    }
    if ( a3 )
      *a3 = v5;
  }
  else
  {
    result = 0;
    if ( a3 )
      *a3 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800038a8  push    rbx
0x1800038aa  push    rbp
0x1800038ab  push    rsi
0x1800038ac  push    rdi
0x1800038ad  mov     r11d, [rcx+4]
0x1800038b1  mov     edi, edx
0x1800038b3  mov     rbp, [rcx+8]
0x1800038b7  test    r11d, r11d
0x1800038ba  jz      short loc_180003933
0x1800038bc  xor     r9d, r9d
0x1800038bf  mov     r10d, r11d
0x1800038c2  test    r11d, r11d
0x1800038c5  jle     short loc_180003927
0x1800038c7  xor     edx, edx
0x1800038c9  mov     ebx, r10d
0x1800038cc  shr     ebx, 1
0x1800038ce  lea     esi, [rbx+r9]
0x1800038d2  movsxd  rax, esi
0x1800038d5  add     rax, rax
0x1800038d8  mov     ecx, [rbp+rax*8+8]
0x1800038dc  cmp     edi, ecx
0x1800038de  setb    dl
0x1800038e1  xor     eax, eax
0x1800038e3  cmp     ecx, edi
0x1800038e5  setb    al
0x1800038e8  cmp     edx, eax
0x1800038ea  jns     short loc_1800038FA
0x1800038ec  or      eax, 0FFFFFFFFh
0x1800038ef  lea     r9d, [rsi+1]
0x1800038f3  sub     eax, ebx
0x1800038f5  add     r10d, eax
0x1800038f8  jmp     short loc_1800038FD
0x1800038fa  mov     r10d, ebx
0x1800038fd  test    r10d, r10d
0x180003900  jg      short loc_1800038C7
0x180003902  cmp     r9d, r11d
0x180003905  jge     short loc_180003927
0x180003907  xor     edx, edx
0x180003909  movsxd  rax, r9d
0x18000390c  add     rax, rax
0x18000390f  mov     ecx, [rbp+rax*8+8]
0x180003913  cmp     edi, ecx
0x180003915  setb    dl
0x180003918  xor     eax, eax
0x18000391a  cmp     ecx, edi
0x18000391c  setb    al
0x18000391f  cmp     eax, edx
0x180003921  js      short loc_180003927
0x180003923  mov     al, 1
0x180003925  jmp     short loc_180003929
0x180003927  xor     al, al
0x180003929  test    r8, r8
0x18000392c  jz      short loc_180003941
0x18000392e  mov     [r8], r9d
0x180003931  jmp     short loc_180003941
0x180003933  xor     al, al
0x180003935  test    r8, r8
0x180003938  jz      short loc_180003941
0x18000393a  mov     dword ptr [r8], 0
0x180003941  pop     rdi
0x180003942  pop     rsi
0x180003943  pop     rbp
0x180003944  pop     rbx
0x180003945  retn
```
