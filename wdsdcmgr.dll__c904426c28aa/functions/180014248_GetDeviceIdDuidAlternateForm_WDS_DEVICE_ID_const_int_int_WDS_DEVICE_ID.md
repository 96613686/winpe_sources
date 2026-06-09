# GetDeviceIdDuidAlternateForm(_WDS_DEVICE_ID const *,int *,int *,_WDS_DEVICE_ID *)

- ea: `0x180014248`
- end: `0x1800143fe`
- name: `?GetDeviceIdDuidAlternateForm@@YAKPEBU_WDS_DEVICE_ID@@PEAH1PEAU1@@Z`
- size: `438`
- prototype: `__int64 __fastcall(const struct _WDS_DEVICE_ID *, int *, int *, struct _WDS_DEVICE_ID *, struct tagDHCPV6_DUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800042f4`

## callees

- `0x180014248`
- `0x1800149a8`
- `0x180014d58`
- `0x180015c85`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001433b`
- `msvcrt!memcpy_s` at `0x18001433b`

## string_xrefs

- `0x1800142e8`: `onecore\base\eco\wds\wdslib\common\src\deviceid.cpp`

## pseudocode

```c
__int64 __fastcall GetDeviceIdDuidAlternateForm(
        const struct _WDS_DEVICE_ID *a1,
        int *a2,
        int *a3,
        struct _WDS_DEVICE_ID *a4,
        struct tagDHCPV6_DUID *a5)
{
  unsigned int v6; // ebp
  unsigned __int64 v7; // rdx
  __int128 v11; // xmm0
  _QWORD *v12; // rbx
  __int64 v13; // rax
  const char *v14; // rdx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  __int64 v18; // r8
  __int64 v19; // rax
  const void *v20; // rdx
  __int64 v21; // rax
  __int128 v22; // xmm0

  v6 = 0;
  v7 = *((_QWORD *)a1 + 16);
  if ( v7 == 6 )
  {
    v11 = *(_OWORD *)a1;
    *a2 = 0;
    *a3 = 0;
    *(_OWORD *)a4 = v11;
    v12 = (_QWORD *)((char *)a4 + 128);
    *((_OWORD *)a4 + 1) = *((_OWORD *)a1 + 1);
    *((_OWORD *)a4 + 2) = *((_OWORD *)a1 + 2);
    *((_OWORD *)a4 + 3) = *((_OWORD *)a1 + 3);
    *((_OWORD *)a4 + 4) = *((_OWORD *)a1 + 4);
    *((_OWORD *)a4 + 5) = *((_OWORD *)a1 + 5);
    *((_OWORD *)a4 + 6) = *((_OWORD *)a1 + 6);
    *((_OWORD *)a4 + 7) = *((_OWORD *)a1 + 7);
    v13 = *((_QWORD *)a1 + 16);
LABEL_15:
    *v12 = v13;
    return v6;
  }
  v6 = ParseDuid((const unsigned __int8 *)a1, v7, a5);
  if ( !ElValidateWin32(v6, v14, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\deviceid.cpp", 0x399u) )
  {
    if ( *((_DWORD *)a5 + 1) && *((_DWORD *)a5 + 2) )
    {
      v15 = *(unsigned __int16 *)a5;
      *a2 = 1;
      v16 = v15 - 1;
      if ( v16 )
      {
        v17 = v16 - 2;
        if ( v17 )
        {
          if ( v17 == 1 )
          {
            v18 = *((_QWORD *)a5 + 2);
            *a3 = 1;
            memcpy_s(a4, 0x80u, (const void *const)(v18 + 2), 0x10u);
            *((_QWORD *)a4 + 16) = 16;
            return v6;
          }
LABEL_14:
          v22 = *(_OWORD *)a1;
          *a3 = 0;
          *(_OWORD *)a4 = v22;
          *((_OWORD *)a4 + 1) = *((_OWORD *)a1 + 1);
          *((_OWORD *)a4 + 2) = *((_OWORD *)a1 + 2);
          *((_OWORD *)a4 + 3) = *((_OWORD *)a1 + 3);
          *((_OWORD *)a4 + 4) = *((_OWORD *)a1 + 4);
          *((_OWORD *)a4 + 5) = *((_OWORD *)a1 + 5);
          *((_OWORD *)a4 + 6) = *((_OWORD *)a1 + 6);
          v12 = (_QWORD *)((char *)a4 + 128);
          *((_OWORD *)v12 - 1) = *((_OWORD *)a1 + 7);
          v13 = *((_QWORD *)a1 + 16);
          goto LABEL_15;
        }
        v19 = *((unsigned __int16 *)a5 + 6);
        *a3 = 1;
        *((_QWORD *)a4 + 16) = v19;
        v20 = (const void *)(*((_QWORD *)a5 + 2) + 4LL);
      }
      else
      {
        v21 = *((unsigned __int16 *)a5 + 6);
        *a3 = 1;
        *((_QWORD *)a4 + 16) = v21;
        v20 = (const void *)(*((_QWORD *)a5 + 2) + 8LL);
      }
      memcpy_0(a4, v20, *((unsigned __int16 *)a5 + 6));
      return v6;
    }
    *a2 = 1;
    goto LABEL_14;
  }
  return v6;
}

```

## disassembly

```asm
0x180014248  mov     [rsp+arg_0], rbx
0x18001424d  mov     [rsp+arg_8], rbp
0x180014252  mov     [rsp+arg_10], rsi
0x180014257  push    rdi
0x180014258  push    r14
0x18001425a  push    r15
0x18001425c  sub     rsp, 20h
0x180014260  mov     r15, rdx
0x180014263  xor     ebp, ebp
0x180014265  mov     rdx, [rcx+80h]; unsigned __int64
0x18001426c  mov     rbx, r9
0x18001426f  mov     r14, r8
0x180014272  mov     rdi, rcx
0x180014275  cmp     rdx, 6
0x180014279  jnz     short loc_1800142D5
0x18001427b  movups  xmm0, xmmword ptr [rcx]
0x18001427e  and     [r15], ebp
0x180014281  lea     eax, [rdx+7Ah]
0x180014284  and     [r8], ebp
0x180014287  movups  xmmword ptr [r9], xmm0
0x18001428b  add     rbx, rax
0x18001428e  movups  xmm1, xmmword ptr [rcx+10h]
0x180014292  movups  xmmword ptr [r9+10h], xmm1
0x180014297  movups  xmm0, xmmword ptr [rcx+20h]
0x18001429b  movups  xmmword ptr [r9+20h], xmm0
0x1800142a0  movups  xmm1, xmmword ptr [rcx+30h]
0x1800142a4  movups  xmmword ptr [r9+30h], xmm1
0x1800142a9  movups  xmm0, xmmword ptr [rcx+40h]
0x1800142ad  movups  xmmword ptr [r9+40h], xmm0
0x1800142b2  movups  xmm1, xmmword ptr [rcx+50h]
0x1800142b6  movups  xmmword ptr [r9+50h], xmm1
0x1800142bb  movups  xmm0, xmmword ptr [rcx+60h]
0x1800142bf  movups  xmmword ptr [r9+60h], xmm0
0x1800142c4  movups  xmm0, xmmword ptr [rcx+70h]
0x1800142c8  movups  xmmword ptr [rbx-10h], xmm0
0x1800142cc  mov     rax, [rcx+rax]
0x1800142d0  jmp     loc_1800143E0
0x1800142d5  mov     rsi, [rsp+38h+arg_20]
0x1800142da  mov     r8, rsi; struct tagDHCPV6_DUID *
0x1800142dd  call    ?ParseDuid@@YAKPEBE_KPEAUtagDHCPV6_DUID@@@Z; ParseDuid(uchar const *,unsigned __int64,tagDHCPV6_DUID *)
0x1800142e2  mov     r9d, 399h; unsigned int
0x1800142e8  lea     r8, aOnecoreBaseEco_3; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800142ef  mov     ecx, eax; unsigned int
0x1800142f1  mov     ebp, eax
0x1800142f3  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800142f8  test    eax, eax
0x1800142fa  jnz     loc_1800143E3
0x180014300  cmp     [rsi+4], eax
0x180014303  jz      loc_18001438A
0x180014309  cmp     [rsi+8], eax
0x18001430c  jz      short loc_18001438A
0x18001430e  movzx   ecx, word ptr [rsi]
0x180014311  lea     edx, [rax+1]
0x180014314  mov     [r15], edx
0x180014317  sub     ecx, edx
0x180014319  jz      short loc_180014365
0x18001431b  sub     ecx, 2
0x18001431e  jz      short loc_18001434D
0x180014320  cmp     ecx, edx
0x180014322  jnz     short loc_180014392
0x180014324  mov     r8, [rsi+10h]
0x180014328  lea     edi, [rax+10h]
0x18001432b  mov     [r14], edx
0x18001432e  add     r8, 2; Source
0x180014332  mov     r9d, edi; SourceSize
0x180014335  lea     edx, [rdi+70h]; DestinationSize
0x180014338  mov     rcx, rbx; Destination
0x18001433b  call    cs:__imp_memcpy_s
0x180014341  mov     [rbx+80h], rdi
0x180014348  jmp     loc_1800143E3
0x18001434d  movzx   eax, word ptr [rsi+0Ch]
0x180014351  mov     [r14], edx
0x180014354  mov     [rbx+80h], rax
0x18001435b  mov     rdx, [rsi+10h]
0x18001435f  add     rdx, 4
0x180014363  jmp     short loc_18001437B
0x180014365  movzx   eax, word ptr [rsi+0Ch]
0x180014369  mov     [r14], edx
0x18001436c  mov     [rbx+80h], rax
0x180014373  mov     rdx, [rsi+10h]
0x180014377  add     rdx, 8; Src
0x18001437b  movzx   r8d, word ptr [rsi+0Ch]; Size
0x180014380  mov     rcx, rbx; void *
0x180014383  call    memcpy_0
0x180014388  jmp     short loc_1800143E3
0x18001438a  mov     edx, 1
0x18001438f  mov     [r15], edx
0x180014392  movups  xmm0, xmmword ptr [rdi]
0x180014395  and     dword ptr [r14], 0
0x180014399  mov     eax, 80h
0x18001439e  movups  xmmword ptr [rbx], xmm0
0x1800143a1  movups  xmm1, xmmword ptr [rdi+10h]
0x1800143a5  movups  xmmword ptr [rbx+10h], xmm1
0x1800143a9  movups  xmm0, xmmword ptr [rdi+20h]
0x1800143ad  movups  xmmword ptr [rbx+20h], xmm0
0x1800143b1  movups  xmm1, xmmword ptr [rdi+30h]
0x1800143b5  movups  xmmword ptr [rbx+30h], xmm1
0x1800143b9  movups  xmm0, xmmword ptr [rdi+40h]
0x1800143bd  movups  xmmword ptr [rbx+40h], xmm0
0x1800143c1  movups  xmm1, xmmword ptr [rdi+50h]
0x1800143c5  movups  xmmword ptr [rbx+50h], xmm1
0x1800143c9  movups  xmm0, xmmword ptr [rdi+60h]
0x1800143cd  movups  xmmword ptr [rbx+60h], xmm0
0x1800143d1  add     rbx, rax
0x1800143d4  movups  xmm0, xmmword ptr [rdi+70h]
0x1800143d8  movups  xmmword ptr [rbx-10h], xmm0
0x1800143dc  mov     rax, [rdi+rax]
0x1800143e0  mov     [rbx], rax
0x1800143e3  mov     rbx, [rsp+38h+arg_0]
0x1800143e8  mov     eax, ebp
0x1800143ea  mov     rbp, [rsp+38h+arg_8]
0x1800143ef  mov     rsi, [rsp+38h+arg_10]
0x1800143f4  add     rsp, 20h
0x1800143f8  pop     r15
0x1800143fa  pop     r14
0x1800143fc  pop     rdi
0x1800143fd  retn
```
