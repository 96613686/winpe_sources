# Windows::Internal::ButtonBarLayout::DoLayout(DirectUI::Element *,int,int)

- ea: `0x1800926d0`
- end: `0x1800928f2`
- name: `?DoLayout@ButtonBarLayout@Internal@Windows@@UEAAXPEAVElement@DirectUI@@HH@Z`
- size: `546`
- prototype: `void __fastcall(Windows::Internal::ButtonBarLayout *__hidden this, struct DirectUI::Element *, int, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18005e6b0`
- `0x1800926d0`

## import_xrefs

- `DUI70!?IsCacheDirty@Layout@DirectUI@@IEAA_NXZ` at `0x1800926f7`
- `DUI70!?IsCacheDirty@Layout@DirectUI@@IEAA_NXZ` at `0x1800926f7`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x18009271c`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x18009271c`
- `DUI70!?GetChildFromLayoutIndex@Layout@DirectUI@@QEAAPEAVElement@2@PEAV32@HPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@@Z` at `0x1800927ec`
- `DUI70!?GetChildFromLayoutIndex@Layout@DirectUI@@QEAAPEAVElement@2@PEAV32@HPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@@Z` at `0x180092843`
- `DUI70!?GetChildFromLayoutIndex@Layout@DirectUI@@QEAAPEAVElement@2@PEAV32@HPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@@Z` at `0x1800927ec`
- `DUI70!?GetChildFromLayoutIndex@Layout@DirectUI@@QEAAPEAVElement@2@PEAV32@HPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@@Z` at `0x180092843`
- `DUI70!?GetLayoutChildCount@Layout@DirectUI@@QEAAIPEAVElement@2@@Z` at `0x180092733`
- `DUI70!?GetLayoutChildCount@Layout@DirectUI@@QEAAIPEAVElement@2@@Z` at `0x180092733`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x180092823`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x18009287a`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x180092823`
- `DUI70!?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z` at `0x18009287a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Internal::ButtonBarLayout::DoLayout(
        Windows::Internal::ButtonBarLayout *this,
        struct DirectUI::Element *a2,
        int a3,
        int a4)
{
  unsigned int LayoutChildCount; // r9d
  char v8; // r8
  int v9; // edi
  int v10; // esi
  int v11; // eax
  int v12; // edx
  int v13; // ecx
  int v14; // r12d
  __int64 v15; // r15
  __int64 v16; // rbp
  struct DirectUI::Element *ChildFromLayoutIndex; // rax
  struct DirectUI::Element *v18; // rax
  int v19; // [rsp+40h] [rbp-58h]
  int v20; // [rsp+44h] [rbp-54h]
  unsigned int v21; // [rsp+48h] [rbp-50h]
  __int64 Children; // [rsp+50h] [rbp-48h]
  _QWORD v23[8]; // [rsp+58h] [rbp-40h] BYREF

  if ( !DirectUI::Layout::IsCacheDirty(this) )
  {
    v23[0] = 0;
    Children = DirectUI::Element::GetChildren(a2, v23);
    LayoutChildCount = DirectUI::Layout::GetLayoutChildCount(this, a2);
    if ( LayoutChildCount )
    {
      v8 = *((_BYTE *)this + 272);
      v9 = a3 - *(_DWORD *)((char *)this + (v8 != 0 ? 4 : 0) + 276);
      v10 = a3;
      if ( *((_DWORD *)this + 70) < a3 )
        v10 = *((_DWORD *)this + 70);
      if ( v9 < 0 )
      {
        v8 = 1;
        *((_BYTE *)this + 272) = 1;
        v11 = 0;
        if ( v10 >= 0 )
          v11 = v10;
        v10 = v11;
        v9 = a3 - v11;
      }
      v21 = LayoutChildCount - 1;
      if ( LayoutChildCount != 1 )
      {
        v12 = 0;
        v19 = 0;
        v13 = 0;
        v20 = 0;
        v14 = 0;
        v15 = 0;
        do
        {
          v16 = 8 * ((unsigned int)v15 + 2 * v15);
          if ( v8 )
          {
            v14 += v13;
          }
          else
          {
            v9 += v12;
            v10 = *(_DWORD *)((char *)this + v16 + 32);
          }
          ChildFromLayoutIndex = (struct DirectUI::Element *)DirectUI::Layout::GetChildFromLayoutIndex(
                                                               this,
                                                               a2,
                                                               (unsigned int)v15,
                                                               Children);
          DirectUI::Layout::UpdateLayoutRect(
            a2,
            a3,
            a4,
            ChildFromLayoutIndex,
            v9,
            v14,
            v10,
            *(_DWORD *)((char *)this + v16 + 36));
          v18 = (struct DirectUI::Element *)DirectUI::Layout::GetChildFromLayoutIndex(
                                              this,
                                              a2,
                                              (unsigned int)(v15 + 1),
                                              Children);
          DirectUI::Layout::UpdateLayoutRect(a2, a3, a4, v18, v9, v14, v10, *(_DWORD *)((char *)this + v16 + 36));
          v8 = *((_BYTE *)this + 272);
          if ( v8 )
          {
            v14 += *(_DWORD *)((char *)this + v16 + 36);
            v13 = *(_DWORD *)((char *)this + v16 + 52);
            v20 = v13;
            v12 = v19;
          }
          else
          {
            v9 += *(_DWORD *)((char *)this + v16 + 32);
            v12 = *((_DWORD *)this + 4 * v15 + 2 * (unsigned int)v15 + 12);
            v19 = v12;
            v13 = v20;
          }
          v15 = (unsigned int)(v15 + 2);
        }
        while ( (unsigned int)v15 < v21 );
      }
    }
    CValuePtr::Release((CValuePtr *)v23);
  }
}

```

## disassembly

```asm
0x1800926d0  mov     [rsp+arg_0], rbx
0x1800926d5  mov     [rsp+arg_18], r9d
0x1800926da  mov     [rsp+arg_8], rdx
0x1800926df  push    rbp
0x1800926e0  push    rsi
0x1800926e1  push    rdi
0x1800926e2  push    r12
0x1800926e4  push    r13
0x1800926e6  push    r14
0x1800926e8  push    r15
0x1800926ea  sub     rsp, 60h
0x1800926ee  mov     r14d, r8d
0x1800926f1  mov     rdi, rdx
0x1800926f4  mov     rbx, rcx
0x1800926f7  call    cs:__imp_?IsCacheDirty@Layout@DirectUI@@IEAA_NXZ; DirectUI::Layout::IsCacheDirty(void)
0x1800926fe  nop     dword ptr [rax+rax+00h]
0x180092703  test    al, al
0x180092705  jnz     loc_1800928D9
0x18009270b  mov     [rsp+98h+var_40], 0
0x180092714  lea     rdx, [rsp+98h+var_40]
0x180092719  mov     rcx, rdi
0x18009271c  call    cs:__imp_?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z; DirectUI::Element::GetChildren(DirectUI::Value * *)
0x180092723  nop     dword ptr [rax+rax+00h]
0x180092728  mov     [rsp+98h+var_48], rax
0x18009272d  mov     rdx, rdi
0x180092730  mov     rcx, rbx
0x180092733  call    cs:__imp_?GetLayoutChildCount@Layout@DirectUI@@QEAAIPEAVElement@2@@Z; DirectUI::Layout::GetLayoutChildCount(DirectUI::Element *)
0x18009273a  nop     dword ptr [rax+rax+00h]
0x18009273f  mov     r9d, eax
0x180092742  test    eax, eax
0x180092744  jz      loc_1800928CF
0x18009274a  mov     r8b, [rbx+110h]
0x180092751  mov     cl, r8b
0x180092754  neg     cl
0x180092756  sbb     rdx, rdx
0x180092759  and     edx, 4
0x18009275c  mov     edi, r14d
0x18009275f  sub     edi, [rdx+rbx+114h]
0x180092766  mov     ecx, [rbx+118h]
0x18009276c  mov     esi, r14d
0x18009276f  cmp     ecx, r14d
0x180092772  cmovl   esi, ecx
0x180092775  test    edi, edi
0x180092777  jns     short loc_180092791
0x180092779  mov     r8b, 1
0x18009277c  mov     [rbx+110h], r8b
0x180092783  xor     eax, eax
0x180092785  test    esi, esi
0x180092787  cmovns  eax, esi
0x18009278a  mov     esi, eax
0x18009278c  mov     edi, r14d
0x18009278f  sub     edi, eax
0x180092791  lea     eax, [r9-1]
0x180092795  mov     [rsp+98h+var_50], eax
0x180092799  test    eax, eax
0x18009279b  jz      loc_1800928CF
0x1800927a1  xor     edx, edx
0x1800927a3  mov     [rsp+98h+var_58], edx
0x1800927a7  xor     ecx, ecx
0x1800927a9  mov     [rsp+98h+var_54], ecx
0x1800927ad  xor     r12d, r12d
0x1800927b0  xor     r15d, r15d
0x1800927b3  mov     r13d, r15d
0x1800927b6  lea     rax, ds:0[r15*2]
0x1800927be  add     rax, r13
0x1800927c1  lea     rbp, ds:0[rax*8]
0x1800927c9  test    r8b, r8b
0x1800927cc  jz      short loc_1800927D3
0x1800927ce  add     r12d, ecx
0x1800927d1  jmp     short loc_1800927D9
0x1800927d3  add     edi, edx
0x1800927d5  mov     esi, [rbx+rbp+20h]
0x1800927d9  mov     r9, [rsp+98h+var_48]
0x1800927de  mov     r8d, r15d
0x1800927e1  mov     rdx, [rsp+98h+arg_8]
0x1800927e9  mov     rcx, rbx
0x1800927ec  call    cs:__imp_?GetChildFromLayoutIndex@Layout@DirectUI@@QEAAPEAVElement@2@PEAV32@HPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@@Z; DirectUI::Layout::GetChildFromLayoutIndex(DirectUI::Element *,int,DirectUI::DynamicArray<DirectUI::Element *,0> *)
0x1800927f3  nop     dword ptr [rax+rax+00h]
0x1800927f8  mov     ecx, [rbx+rbp+24h]
0x1800927fc  mov     [rsp+98h+var_60], ecx
0x180092800  mov     [rsp+98h+var_68], esi
0x180092804  mov     [rsp+98h+var_70], r12d
0x180092809  mov     [rsp+98h+var_78], edi
0x18009280d  mov     r9, rax
0x180092810  mov     r8d, [rsp+98h+arg_18]
0x180092818  mov     edx, r14d
0x18009281b  mov     rcx, [rsp+98h+arg_8]
0x180092823  call    cs:__imp_?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z; DirectUI::Layout::UpdateLayoutRect(DirectUI::Element *,int,int,DirectUI::Element *,int,int,int,int)
0x18009282a  nop     dword ptr [rax+rax+00h]
0x18009282f  lea     r8d, [r15+1]
0x180092833  mov     r9, [rsp+98h+var_48]
0x180092838  mov     rdx, [rsp+98h+arg_8]
0x180092840  mov     rcx, rbx
0x180092843  call    cs:__imp_?GetChildFromLayoutIndex@Layout@DirectUI@@QEAAPEAVElement@2@PEAV32@HPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@@Z; DirectUI::Layout::GetChildFromLayoutIndex(DirectUI::Element *,int,DirectUI::DynamicArray<DirectUI::Element *,0> *)
0x18009284a  nop     dword ptr [rax+rax+00h]
0x18009284f  mov     ecx, [rbx+rbp+24h]
0x180092853  mov     [rsp+98h+var_60], ecx
0x180092857  mov     [rsp+98h+var_68], esi
0x18009285b  mov     [rsp+98h+var_70], r12d
0x180092860  mov     [rsp+98h+var_78], edi
0x180092864  mov     r9, rax
0x180092867  mov     r8d, [rsp+98h+arg_18]
0x18009286f  mov     edx, r14d
0x180092872  mov     rcx, [rsp+98h+arg_8]
0x18009287a  call    cs:__imp_?UpdateLayoutRect@Layout@DirectUI@@SAXPEAVElement@2@HH0HHHH@Z; DirectUI::Layout::UpdateLayoutRect(DirectUI::Element *,int,int,DirectUI::Element *,int,int,int,int)
0x180092881  nop     dword ptr [rax+rax+00h]
0x180092886  mov     r8b, [rbx+110h]
0x18009288d  test    r8b, r8b
0x180092890  jz      short loc_1800928A5
0x180092892  add     r12d, [rbx+rbp+24h]
0x180092897  mov     ecx, [rbx+rbp+34h]
0x18009289b  mov     [rsp+98h+var_54], ecx
0x18009289f  mov     edx, [rsp+98h+var_58]
0x1800928a3  jmp     short loc_1800928C0
0x1800928a5  add     edi, [rbx+rbp+20h]
0x1800928a9  lea     rax, ds:0[r15*2]
0x1800928b1  add     rax, r13
0x1800928b4  mov     edx, [rbx+rax*8+30h]
0x1800928b8  mov     [rsp+98h+var_58], edx
0x1800928bc  mov     ecx, [rsp+98h+var_54]
0x1800928c0  add     r15d, 2
0x1800928c4  cmp     r15d, [rsp+98h+var_50]
0x1800928c9  jb      loc_1800927B3
0x1800928cf  lea     rcx, [rsp+98h+var_40]; this
0x1800928d4  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x1800928d9  mov     rbx, [rsp+98h+arg_0]
0x1800928e1  add     rsp, 60h
0x1800928e5  pop     r15
0x1800928e7  pop     r14
0x1800928e9  pop     r13
0x1800928eb  pop     r12
0x1800928ed  pop     rdi
0x1800928ee  pop     rsi
0x1800928ef  pop     rbp
0x1800928f0  retn
```
