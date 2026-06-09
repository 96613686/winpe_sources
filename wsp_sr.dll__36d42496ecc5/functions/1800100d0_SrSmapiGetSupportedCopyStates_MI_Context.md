# SrSmapiGetSupportedCopyStates(_MI_Context *)

- ea: `0x1800100d0`
- end: `0x1800102b3`
- name: `?SrSmapiGetSupportedCopyStates@@YA?AW4_MI_Result@@PEAU_MI_Context@@@Z`
- size: `483`
- prototype: `__int64 __fastcall(struct _MI_Context *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180004350`

## callees

- `0x1800014e0`
- `0x180001e08`
- `0x18000570c`
- `0x1800058f8`
- `0x180005910`
- `0x180005cac`
- `0x1800066d8`
- `0x180008df8`
- `0x18000e02c`
- `0x1800100d0`
- `0x18002d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SrSmapiGetSupportedCopyStates(struct _MI_Context *a1)
{
  MI_Uint32 v2; // ebx
  int v3; // r14d
  int v4; // eax
  int v5; // esi
  __int16 v7; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v8; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v9; // [rsp+48h] [rbp-B8h]
  __int64 v10; // [rsp+50h] [rbp-B0h] BYREF
  int v11; // [rsp+58h] [rbp-A8h]
  int v12; // [rsp+5Ch] [rbp-A4h]
  MI_Instance self; // [rsp+60h] [rbp-A0h] BYREF
  int v14; // [rsp+A0h] [rbp-60h]
  char v15; // [rsp+A4h] [rbp-5Ch]
  _QWORD v16[2]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v17[32]; // [rsp+F0h] [rbp-10h] BYREF
  int v18; // [rsp+110h] [rbp+10h]

  CWMIContext::CWMIContext((CWMIContext *)v16, a1);
  std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(&v8);
  self.ft = 0;
  memset_0(&self.classDecl, 0, 0x70u);
  v7 = 2;
  std::vector<unsigned short>::push_back(&v8, &v7);
  v2 = 4;
  v7 = 4;
  std::vector<unsigned short>::push_back(&v8, &v7);
  v7 = 5;
  std::vector<unsigned short>::push_back(&v8, &v7);
  v3 = (__int64)(*((_QWORD *)&v8 + 1) - v8) >> 1;
  if ( (unsigned __int64)((__int64)(*((_QWORD *)&v8 + 1) - v8) >> 1) > 0xFFFFFFFF )
  {
    v2 = 1;
    goto LABEL_13;
  }
  if ( a1 && a1->ft )
  {
    v4 = ((__int64 (__fastcall *)(struct _MI_Context *, __int64 *, MI_Instance *))a1->ft->ConstructParameters)(
           a1,
           &WSP_ReplicationCapabilities_GetSupportedCopyStates_rtti,
           &self);
    v5 = v4;
    if ( !v4 )
    {
      v12 = 0;
      v10 = v8;
      v11 = v3;
      v4 = ((__int64 (__fastcall *)(MI_Instance *, __int64, __int64 *, __int64, _DWORD))self.ft->SetElementAt)(
             &self,
             2,
             &v10,
             19,
             0);
      if ( !v4 )
      {
        v14 = v18;
        v15 = 1;
        if ( !a1->ft )
          goto LABEL_11;
        v4 = ((__int64 (__fastcall *)(struct _MI_Context *, MI_Instance *))a1->ft->PostInstance)(a1, &self);
      }
    }
  }
  else
  {
    v5 = 4;
    v4 = 4;
  }
  v2 = v4;
LABEL_11:
  if ( !v5 )
    MI_Instance_Destruct(&self);
LABEL_13:
  CWMIContext::EvaluateErrorsAndPostResult((CWMIContext *)v16, v2);
  if ( (_QWORD)v8 )
  {
    std::_Deallocate<16>((void *)v8, 2 * ((v9 - (__int64)v8) >> 1));
    v8 = 0;
    v9 = 0;
  }
  v16[0] = &CWMIContext::`vftable';
  std::wstring::_Tidy_deallocate((__int64)v17);
  return v2;
}

```

## disassembly

```asm
0x1800100d0  push    rbp
0x1800100d2  push    rbx
0x1800100d3  push    rsi
0x1800100d4  push    rdi
0x1800100d5  push    r12
0x1800100d7  push    r14
0x1800100d9  lea     rbp, [rsp-48h]
0x1800100de  sub     rsp, 148h
0x1800100e5  mov     rax, cs:__security_cookie
0x1800100ec  xor     rax, rsp
0x1800100ef  mov     [rbp+70h+var_40], rax
0x1800100f3  mov     rdi, rcx
0x1800100f6  mov     rdx, rcx; struct _MI_Context *
0x1800100f9  lea     rcx, [rbp+70h+var_90]; this
0x1800100fd  call    ??0CWMIContext@@QEAA@PEAU_MI_Context@@@Z; CWMIContext::CWMIContext(_MI_Context *)
0x180010102  nop
0x180010103  lea     rcx, [rsp+170h+var_138]
0x180010108  call    ??0?$vector@VMSFT_StorageNode@srstor@@V?$allocator@VMSFT_StorageNode@srstor@@@std@@@std@@QEAA@XZ; std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(void)
0x18001010d  nop
0x18001010e  mov     [rsp+170h+self.ft], 0
0x180010117  xor     edx, edx; Val
0x180010119  lea     r8d, [rdx+70h]; Size
0x18001011d  lea     rcx, [rsp+170h+self.classDecl]; void *
0x180010122  call    memset_0
0x180010127  mov     r12d, 2
0x18001012d  mov     [rsp+170h+var_140], r12w
0x180010133  lea     rdx, [rsp+170h+var_140]
0x180010138  lea     rcx, [rsp+170h+var_138]
0x18001013d  call    ?push_back@?$vector@GV?$allocator@G@std@@@std@@QEAAX$$QEAG@Z; std::vector<ushort>::push_back(ushort &&)
0x180010142  lea     ebx, [r12+2]
0x180010147  mov     [rsp+170h+var_140], bx
0x18001014c  lea     rdx, [rsp+170h+var_140]
0x180010151  lea     rcx, [rsp+170h+var_138]
0x180010156  call    ?push_back@?$vector@GV?$allocator@G@std@@@std@@QEAAX$$QEAG@Z; std::vector<ushort>::push_back(ushort &&)
0x18001015b  lea     eax, [rbx+1]
0x18001015e  mov     [rsp+170h+var_140], ax
0x180010163  lea     rdx, [rsp+170h+var_140]
0x180010168  lea     rcx, [rsp+170h+var_138]
0x18001016d  call    ?push_back@?$vector@GV?$allocator@G@std@@@std@@QEAAX$$QEAG@Z; std::vector<ushort>::push_back(ushort &&)
0x180010172  mov     rcx, qword ptr [rsp+170h+var_138+8]
0x180010177  sub     rcx, qword ptr [rsp+170h+var_138]
0x18001017c  sar     rcx, 1
0x18001017f  xor     edx, edx
0x180010181  mov     r8d, 0FFFFFFFFh
0x180010187  cmp     rcx, r8
0x18001018a  setnbe  dl
0x18001018d  mov     r14d, ecx
0x180010190  xor     eax, eax
0x180010192  cmp     rcx, r8
0x180010195  cmova   r14d, eax
0x180010199  ja      loc_180010244
0x18001019f  test    rdi, rdi
0x1800101a2  jz      loc_18001022E
0x1800101a8  mov     rax, [rdi]
0x1800101ab  test    rax, rax
0x1800101ae  jz      short loc_18001022E
0x1800101b0  lea     r8, [rsp+170h+self]
0x1800101b5  lea     rdx, WSP_ReplicationCapabilities_GetSupportedCopyStates_rtti
0x1800101bc  mov     rcx, rdi
0x1800101bf  mov     rax, [rax+20h]
0x1800101c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101c8  mov     esi, eax
0x1800101ca  test    eax, eax
0x1800101cc  jnz     short loc_180010232
0x1800101ce  mov     [rsp+170h+var_114], eax
0x1800101d2  mov     rcx, qword ptr [rsp+170h+var_138]
0x1800101d7  mov     [rsp+170h+var_120], rcx
0x1800101dc  mov     [rsp+170h+var_118], r14d
0x1800101e1  mov     rcx, [rsp+170h+self.ft]
0x1800101e6  mov     rax, [rcx+50h]
0x1800101ea  mov     [rsp+170h+var_150], esi
0x1800101ee  lea     r9d, [r12+11h]
0x1800101f3  lea     r8, [rsp+170h+var_120]
0x1800101f8  mov     edx, r12d
0x1800101fb  lea     rcx, [rsp+170h+self]
0x180010200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010205  test    eax, eax
0x180010207  jnz     short loc_180010232
0x180010209  mov     ecx, [rbp+70h+var_60]
0x18001020c  mov     [rbp+70h+var_D0], ecx
0x18001020f  mov     [rbp+70h+var_CC], 1
0x180010213  mov     rax, [rdi]
0x180010216  test    rax, rax
0x180010219  jz      short loc_180010234
0x18001021b  lea     rdx, [rsp+170h+self]
0x180010220  mov     rcx, rdi
0x180010223  mov     rax, [rax+8]
0x180010227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001022c  jmp     short loc_180010232
0x18001022e  mov     esi, ebx
0x180010230  mov     eax, ebx
0x180010232  mov     ebx, eax
0x180010234  test    esi, esi
0x180010236  jnz     short loc_180010246
0x180010238  lea     rcx, [rsp+170h+self]; self
0x18001023d  call    MI_Instance_Destruct
0x180010242  jmp     short loc_180010246
0x180010244  mov     ebx, edx
0x180010246  mov     edx, ebx; enum _MI_Result
0x180010248  lea     rcx, [rbp+70h+var_90]; this
0x18001024c  call    ?EvaluateErrorsAndPostResult@CWMIContext@@QEAAXW4_MI_Result@@@Z; CWMIContext::EvaluateErrorsAndPostResult(_MI_Result)
0x180010251  nop
0x180010252  mov     rcx, qword ptr [rsp+170h+var_138]
0x180010257  test    rcx, rcx
0x18001025a  jz      short loc_180010281
0x18001025c  mov     rdx, [rsp+170h+var_128]
0x180010261  sub     rdx, rcx
0x180010264  sar     rdx, 1
0x180010267  add     rdx, rdx
0x18001026a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001026f  xorps   xmm0, xmm0
0x180010272  movdqu  [rsp+170h+var_138], xmm0
0x180010278  mov     [rsp+170h+var_128], 0
0x180010281  lea     rax, ??_7CWMIContext@@6B@; const CWMIContext::`vftable'
0x180010288  mov     [rbp+70h+var_90], rax
0x18001028c  lea     rcx, [rbp+70h+var_80]
0x180010290  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010295  mov     eax, ebx
0x180010297  mov     rcx, [rbp+70h+var_40]
0x18001029b  xor     rcx, rsp; StackCookie
0x18001029e  call    __security_check_cookie
0x1800102a3  add     rsp, 148h
0x1800102aa  pop     r14
0x1800102ac  pop     r12
0x1800102ae  pop     rdi
0x1800102af  pop     rsi
0x1800102b0  pop     rbx
0x1800102b1  pop     rbp
0x1800102b2  retn
```
