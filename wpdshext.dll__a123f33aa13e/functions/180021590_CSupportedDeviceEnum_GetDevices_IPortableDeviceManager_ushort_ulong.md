# CSupportedDeviceEnum::_GetDevices(IPortableDeviceManager *,ushort * * *,ulong *)

- ea: `0x180021590`
- end: `0x1800217eb`
- name: `?_GetDevices@CSupportedDeviceEnum@@AEAAJPEAUIPortableDeviceManager@@PEAPEAPEAGPEAK@Z`
- size: `603`
- prototype: `__int64 __fastcall(CSupportedDeviceEnum *__hidden this, struct IPortableDeviceManager *, unsigned __int16 ***, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000d63c`

## callees

- `0x180021590`
- `0x18002ff5c`
- `0x180055dd0`
- `0x180078010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002174e`
- `ole32!CoTaskMemFree` at `0x180021765`
- `ole32!CoTaskMemFree` at `0x18002174e`
- `ole32!CoTaskMemFree` at `0x180021765`
- `ole32!CoTaskMemAlloc` at `0x18002168b`
- `ole32!CoTaskMemAlloc` at `0x18002168b`

## pseudocode

```c
__int64 __fastcall CSupportedDeviceEnum::_GetDevices(
        CSupportedDeviceEnum *this,
        struct IPortableDeviceManager *a2,
        unsigned __int16 ***a3,
        unsigned int *a4)
{
  unsigned int v7; // ebx
  unsigned int v8; // ebp
  unsigned __int16 **v9; // rdi
  int v10; // eax
  PVOID *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // r8
  unsigned __int64 v15; // rax
  unsigned __int16 **v16; // rax
  __int64 i; // rsi
  unsigned __int16 *v18; // rcx
  int v20; // [rsp+60h] [rbp+8h] BYREF
  int v21; // [rsp+64h] [rbp+Ch]
  int v22; // [rsp+68h] [rbp+10h] BYREF

  v21 = HIDWORD(this);
  v20 = 0;
  v22 = 0;
  if ( !a2 || !a3 || !a4 )
  {
    v7 = -2147024809;
    goto LABEL_38;
  }
  v8 = 0;
  v9 = 0;
  v10 = ((__int64 (__fastcall *)(struct IPortableDeviceManager *, _QWORD, int *))a2->lpVtbl->GetDevices)(a2, 0, &v20);
  v7 = v10;
  if ( v10 < 0 )
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v12 = 26;
LABEL_25:
      WPP_SF_d(v11[2], v12, &WPP_4c5c7f3938733de8a31e3bcf2fcf3406_Traceguids, (unsigned int)v10);
      v11 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_26;
    }
    goto LABEL_26;
  }
  v10 = ((__int64 (__fastcall *)(struct IPortableDeviceManager *, _QWORD, int *))a2->lpVtbl->GetPrivateDevices)(
          a2,
          0,
          &v22);
  v7 = v10;
  if ( v10 >= 0 )
  {
    v8 = v20 + v22;
    v15 = 8LL * (unsigned int)(v20 + v22);
    if ( v15 > 0xFFFFFFFF )
    {
      v7 = -2147024362;
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v7;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_39;
      WPP_SF_DDd(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, v14, v8);
    }
    else
    {
      v16 = (unsigned __int16 **)CoTaskMemAlloc((unsigned int)v15);
      v9 = v16;
      if ( v16 )
      {
        v10 = ((__int64 (__fastcall *)(struct IPortableDeviceManager *, unsigned __int16 **, int *))a2->lpVtbl->GetDevices)(
                a2,
                v16,
                &v20);
        v7 = v10;
        if ( v10 >= 0 )
        {
          v10 = ((__int64 (__fastcall *)(struct IPortableDeviceManager *, unsigned __int16 **, int *))a2->lpVtbl->GetPrivateDevices)(
                  a2,
                  &v9[v20],
                  &v22);
          v7 = v10;
          if ( v10 >= 0 )
          {
            *a3 = v9;
            *a4 = v8;
            return v7;
          }
          v11 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v12 = 30;
            goto LABEL_25;
          }
        }
        else
        {
          v11 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v12 = 29;
            goto LABEL_25;
          }
        }
        goto LABEL_26;
      }
      v7 = -2147024882;
    }
LABEL_38:
    v11 = (PVOID *)WPP_GLOBAL_Control;
LABEL_39:
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 2) != 0 )
      WPP_SF_d(v11[2], 31, &WPP_4c5c7f3938733de8a31e3bcf2fcf3406_Traceguids, v7);
    return v7;
  }
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v12 = 27;
    goto LABEL_25;
  }
LABEL_26:
  if ( v9 )
  {
    for ( i = 0; (unsigned int)i < v8; i = (unsigned int)(i + 1) )
    {
      v18 = v9[i];
      if ( v18 )
      {
        CoTaskMemFree(v18);
        v9[i] = 0;
      }
    }
    CoTaskMemFree(v9);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (v7 & 0x80000000) != 0 )
    goto LABEL_39;
  return v7;
}

```

## disassembly

```asm
0x180021590  mov     rax, rsp
0x180021593  mov     [rax+18h], rbx
0x180021597  mov     [rax+8], rcx
0x18002159b  push    rbp
0x18002159c  push    rsi
0x18002159d  push    rdi
0x18002159e  push    r14
0x1800215a0  push    r15
0x1800215a2  sub     rsp, 30h
0x1800215a6  mov     dword ptr [rax+8], 0
0x1800215ad  mov     r14, r9
0x1800215b0  mov     dword ptr [rax+10h], 0
0x1800215b7  mov     r15, r8
0x1800215ba  mov     rsi, rdx
0x1800215bd  test    rdx, rdx
0x1800215c0  jnz     short loc_1800215D3
0x1800215c2  mov     ebx, 80070057h
0x1800215c7  lea     r15, WPP_GLOBAL_Control
0x1800215ce  jmp     loc_1800217AE
0x1800215d3  test    r15, r15
0x1800215d6  jz      short loc_1800215C2
0x1800215d8  test    r14, r14
0x1800215db  jz      short loc_1800215C2
0x1800215dd  mov     rax, [rdx]
0x1800215e0  lea     r8, [rsp+58h+arg_0]
0x1800215e5  xor     edx, edx
0x1800215e7  mov     rcx, rsi
0x1800215ea  xor     ebp, ebp
0x1800215ec  xor     edi, edi
0x1800215ee  mov     rax, [rax+18h]
0x1800215f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800215f7  mov     ebx, eax
0x1800215f9  test    eax, eax
0x1800215fb  jns     short loc_180021626
0x1800215fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180021604  lea     r15, WPP_GLOBAL_Control
0x18002160b  cmp     rcx, r15
0x18002160e  jz      loc_18002173A
0x180021614  test    byte ptr [rcx+1Ch], 2
0x180021618  jz      loc_18002173A
0x18002161e  lea     edx, [rbp+1Ah]
0x180021621  jmp     loc_180021720
0x180021626  mov     rax, [rsi]
0x180021629  lea     r8, [rsp+58h+arg_8]
0x18002162e  xor     edx, edx
0x180021630  mov     rcx, rsi
0x180021633  mov     rax, [rax+48h]
0x180021637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002163c  mov     ebx, eax
0x18002163e  test    eax, eax
0x180021640  jns     short loc_18002166D
0x180021642  mov     rcx, cs:WPP_GLOBAL_Control
0x180021649  lea     r15, WPP_GLOBAL_Control
0x180021650  cmp     rcx, r15
0x180021653  jz      loc_18002173A
0x180021659  test    byte ptr [rcx+1Ch], 2
0x18002165d  jz      loc_18002173A
0x180021663  mov     edx, 1Bh
0x180021668  jmp     loc_180021720
0x18002166d  mov     ebp, [rsp+58h+arg_8]
0x180021671  mov     ecx, 0FFFFFFFFh
0x180021676  add     ebp, [rsp+58h+arg_0]
0x18002167a  mov     eax, ebp
0x18002167c  shl     rax, 3
0x180021680  cmp     rax, rcx
0x180021683  ja      loc_180021780
0x180021689  mov     ecx, eax; cb
0x18002168b  call    cs:__imp_CoTaskMemAlloc
0x180021691  mov     rdi, rax
0x180021694  test    rax, rax
0x180021697  jnz     short loc_1800216A3
0x180021699  mov     ebx, 8007000Eh
0x18002169e  jmp     loc_1800215C7
0x1800216a3  mov     rax, [rsi]
0x1800216a6  lea     r8, [rsp+58h+arg_0]
0x1800216ab  mov     rdx, rdi
0x1800216ae  mov     rcx, rsi
0x1800216b1  mov     rax, [rax+18h]
0x1800216b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800216ba  mov     ebx, eax
0x1800216bc  test    eax, eax
0x1800216be  jns     short loc_1800216E0
0x1800216c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800216c7  lea     r15, WPP_GLOBAL_Control
0x1800216ce  cmp     rcx, r15
0x1800216d1  jz      short loc_18002173A
0x1800216d3  test    byte ptr [rcx+1Ch], 2
0x1800216d7  jz      short loc_18002173A
0x1800216d9  mov     edx, 1Dh
0x1800216de  jmp     short loc_180021720
0x1800216e0  mov     eax, [rsp+58h+arg_0]
0x1800216e4  lea     r8, [rsp+58h+arg_8]
0x1800216e9  mov     rcx, [rsi]
0x1800216ec  lea     rdx, [rdi+rax*8]
0x1800216f0  mov     rax, [rcx+48h]
0x1800216f4  mov     rcx, rsi
0x1800216f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800216fc  mov     ebx, eax
0x1800216fe  test    eax, eax
0x180021700  jns     short loc_180021778
0x180021702  mov     rcx, cs:WPP_GLOBAL_Control
0x180021709  lea     r15, WPP_GLOBAL_Control
0x180021710  cmp     rcx, r15
0x180021713  jz      short loc_18002173A
0x180021715  test    byte ptr [rcx+1Ch], 2
0x180021719  jz      short loc_18002173A
0x18002171b  mov     edx, 1Eh
0x180021720  mov     rcx, [rcx+10h]
0x180021724  lea     r8, WPP_4c5c7f3938733de8a31e3bcf2fcf3406_Traceguids
0x18002172b  mov     r9d, eax
0x18002172e  call    WPP_SF_d
0x180021733  mov     rcx, cs:WPP_GLOBAL_Control
0x18002173a  test    rdi, rdi
0x18002173d  jz      short loc_180021772
0x18002173f  xor     esi, esi
0x180021741  test    ebp, ebp
0x180021743  jz      short loc_180021762
0x180021745  mov     rcx, [rdi+rsi*8]; pv
0x180021749  test    rcx, rcx
0x18002174c  jz      short loc_18002175C
0x18002174e  call    cs:__imp_CoTaskMemFree
0x180021754  mov     qword ptr [rdi+rsi*8], 0
0x18002175c  inc     esi
0x18002175e  cmp     esi, ebp
0x180021760  jb      short loc_180021745
0x180021762  mov     rcx, rdi; pv
0x180021765  call    cs:__imp_CoTaskMemFree
0x18002176b  mov     rcx, cs:WPP_GLOBAL_Control
0x180021772  test    ebx, ebx
0x180021774  js      short loc_1800217B5
0x180021776  jmp     short loc_1800217D8
0x180021778  mov     [r15], rdi
0x18002177b  mov     [r14], ebp
0x18002177e  jmp     short loc_1800217D8
0x180021780  mov     ebx, 80070216h
0x180021785  mov     rcx, cs:WPP_GLOBAL_Control
0x18002178c  lea     r15, WPP_GLOBAL_Control
0x180021793  cmp     rcx, r15
0x180021796  jz      short loc_1800217D8
0x180021798  test    byte ptr [rcx+1Ch], 2
0x18002179c  jz      short loc_1800217B5
0x18002179e  mov     rcx, [rcx+10h]
0x1800217a2  mov     r9d, ebp
0x1800217a5  mov     [rsp+58h+var_30], ebx
0x1800217a9  call    WPP_SF_DDd
0x1800217ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800217b5  cmp     rcx, r15
0x1800217b8  jz      short loc_1800217D8
0x1800217ba  test    byte ptr [rcx+1Ch], 2
0x1800217be  jz      short loc_1800217D8
0x1800217c0  mov     rcx, [rcx+10h]
0x1800217c4  lea     r8, WPP_4c5c7f3938733de8a31e3bcf2fcf3406_Traceguids
0x1800217cb  mov     edx, 1Fh
0x1800217d0  mov     r9d, ebx
0x1800217d3  call    WPP_SF_d
0x1800217d8  mov     eax, ebx
0x1800217da  mov     rbx, [rsp+58h+arg_10]
0x1800217df  add     rsp, 30h
0x1800217e3  pop     r15
0x1800217e5  pop     r14
0x1800217e7  pop     rdi
0x1800217e8  pop     rsi
0x1800217e9  pop     rbp
0x1800217ea  retn
```
