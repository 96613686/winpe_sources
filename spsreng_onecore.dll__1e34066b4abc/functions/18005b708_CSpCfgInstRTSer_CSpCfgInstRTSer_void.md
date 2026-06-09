# CSpCfgInstRTSer::~CSpCfgInstRTSer(void)

- ea: `0x18005b708`
- end: `0x18005b7da`
- name: `??1CSpCfgInstRTSer@@UEAA@XZ`
- size: `210`
- prototype: `void __fastcall(CSpCfgInstRTSer *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18005ba90`

## callees

- `0x180002e00`
- `0x18000627c`
- `0x180006abc`
- `0x18005b658`
- `0x18005b708`
- `0x18005b954`
- `0x18005eedc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b757`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005b757`

## pseudocode

```c
void __fastcall CSpCfgInstRTSer::~CSpCfgInstRTSer(CSpCfgInstRTSer *this)
{
  unsigned int v2; // edx
  void *v3; // rcx
  void *v4; // rcx
  __int64 v5; // rdi
  CNGramRuleRTSer *v6; // rcx
  void *v7; // rcx

  *(_QWORD *)this = &CSpCfgInstRTSer::`vftable';
  CSpCfgInst::RemoveTextBuffers(this);
  v3 = (void *)*((_QWORD *)this + 77);
  if ( v3 )
  {
    CAllocOnSpecificHeapBase::operator_delete(v3);
    *((_QWORD *)this + 77) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 3);
  if ( v4 && *((_BYTE *)this + 624) )
    CoTaskMemFree(v4);
  v5 = 0;
  for ( *((_QWORD *)this + 3) = 0; (unsigned int)v5 < *((_DWORD *)this + 164); v5 = (unsigned int)(v5 + 1) )
  {
    v6 = *(CNGramRuleRTSer **)(*((_QWORD *)this + 80) + 8 * v5);
    if ( v6 )
    {
      CNGramRuleRTSer::`scalar deleting destructor'(v6, v2);
      *(_QWORD *)(*((_QWORD *)this + 80) + 8 * v5) = 0;
    }
  }
  v7 = (void *)*((_QWORD *)this + 84);
  *((_QWORD *)this + 83) = &CSPHash<unsigned long,unsigned long>::`vftable';
  operator delete(v7);
  CGrowableArrayVoid::~CGrowableArrayVoid((CSpCfgInstRTSer *)((char *)this + 632));
  CSpCfgInstRT::~CSpCfgInstRT(this);
}

```

## disassembly

```asm
0x18005b708  mov     [rsp+arg_0], rbx
0x18005b70d  mov     [rsp+arg_8], rsi
0x18005b712  push    rdi
0x18005b713  sub     rsp, 20h
0x18005b717  lea     rax, ??_7CSpCfgInstRTSer@@6B@; const CSpCfgInstRTSer::`vftable'
0x18005b71e  mov     rbx, rcx
0x18005b721  mov     [rcx], rax
0x18005b724  call    ?RemoveTextBuffers@CSpCfgInst@@IEAAXXZ; CSpCfgInst::RemoveTextBuffers(void)
0x18005b729  mov     rcx, [rbx+268h]; void *
0x18005b730  test    rcx, rcx
0x18005b733  jz      short loc_18005B745
0x18005b735  call    ?operator_delete@CAllocOnSpecificHeapBase@@SAXPEAX@Z; CAllocOnSpecificHeapBase::operator_delete(void *)
0x18005b73a  mov     qword ptr [rbx+268h], 0
0x18005b745  mov     rcx, [rbx+18h]; pv
0x18005b749  test    rcx, rcx
0x18005b74c  jz      short loc_18005B75D
0x18005b74e  cmp     byte ptr [rbx+270h], 0
0x18005b755  jz      short loc_18005B75D
0x18005b757  call    cs:__imp_CoTaskMemFree
0x18005b75d  xor     edi, edi
0x18005b75f  mov     qword ptr [rbx+18h], 0
0x18005b767  cmp     [rbx+290h], edi
0x18005b76d  jbe     short loc_18005B79D
0x18005b76f  mov     rax, [rbx+280h]
0x18005b776  mov     rcx, [rax+rdi*8]; this
0x18005b77a  test    rcx, rcx
0x18005b77d  jz      short loc_18005B793
0x18005b77f  call    ??_GCNGramRuleRTSer@@QEAAPEAXI@Z; CNGramRuleRTSer::`scalar deleting destructor'(uint)
0x18005b784  mov     rax, [rbx+280h]
0x18005b78b  mov     qword ptr [rax+rdi*8], 0
0x18005b793  inc     edi
0x18005b795  cmp     edi, [rbx+290h]
0x18005b79b  jb      short loc_18005B76F
0x18005b79d  mov     rcx, [rbx+2A0h]; void *
0x18005b7a4  lea     rax, ??_7?$CSPHash@KK@@6B@; const CSPHash<ulong,ulong>::`vftable'
0x18005b7ab  mov     [rbx+298h], rax
0x18005b7b2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005b7b7  lea     rcx, [rbx+278h]; this
0x18005b7be  call    ??1CGrowableArrayVoid@@QEAA@XZ; CGrowableArrayVoid::~CGrowableArrayVoid(void)
0x18005b7c3  mov     rcx, rbx; this
0x18005b7c6  mov     rbx, [rsp+28h+arg_0]
0x18005b7cb  mov     rsi, [rsp+28h+arg_8]
0x18005b7d0  add     rsp, 20h
0x18005b7d4  pop     rdi
0x18005b7d5  jmp     ??1CSpCfgInstRT@@UEAA@XZ; CSpCfgInstRT::~CSpCfgInstRT(void)
```
