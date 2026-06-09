# CBlbRestoreFilesAsync::FinalRelease(void)

- ea: `0x140071174`
- end: `0x140071322`
- name: `?FinalRelease@CBlbRestoreFilesAsync@@QEAAXXZ`
- size: `430`
- prototype: `void __fastcall(CBlbRestoreFilesAsync *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task`

## callers

- `0x14003e0d4`

## callees

- `0x140006d88`
- `0x14000753c`
- `0x14000bb24`
- `0x140071174`
- `0x140098c04`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1400711f3`
- `ole32!CoTaskMemFree` at `0x140071210`
- `ole32!CoTaskMemFree` at `0x14007122d`
- `ole32!CoTaskMemFree` at `0x14007124a`
- `ole32!CoTaskMemFree` at `0x140071267`
- `ole32!CoTaskMemFree` at `0x140071284`
- `ole32!CoTaskMemFree` at `0x1400712a1`
- `ole32!CoTaskMemFree` at `0x1400711f3`
- `ole32!CoTaskMemFree` at `0x140071210`
- `ole32!CoTaskMemFree` at `0x14007122d`
- `ole32!CoTaskMemFree` at `0x14007124a`
- `ole32!CoTaskMemFree` at `0x140071267`
- `ole32!CoTaskMemFree` at `0x140071284`
- `ole32!CoTaskMemFree` at `0x1400712a1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CBlbRestoreFilesAsync::FinalRelease(CBlbRestoreFilesAsync *this)
{
  char *v2; // rcx
  char *v3; // rbx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  __int64 v11; // rax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
  }
  v2 = (char *)*((_QWORD *)this + 28);
  if ( v2 )
  {
    v3 = v2 - 8;
    `eh vector destructor iterator'(
      v2,
      0x48u,
      *((_QWORD *)v2 - 1),
      (void (*)(void *))CBlbRestoreFileContext::~CBlbRestoreFileContext);
    operator delete[](v3);
  }
  v4 = (void *)*((_QWORD *)this + 34);
  if ( v4 )
  {
    CoTaskMemFree(v4);
    *((_QWORD *)this + 34) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 35);
  if ( v5 )
  {
    CoTaskMemFree(v5);
    *((_QWORD *)this + 35) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 36);
  if ( v6 )
  {
    CoTaskMemFree(v6);
    *((_QWORD *)this + 36) = 0;
  }
  v7 = (void *)*((_QWORD *)this + 37);
  if ( v7 )
  {
    CoTaskMemFree(v7);
    *((_QWORD *)this + 37) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 26);
  if ( v8 )
  {
    CoTaskMemFree(v8);
    *((_QWORD *)this + 26) = 0;
  }
  v9 = (void *)*((_QWORD *)this + 27);
  if ( v9 )
  {
    CoTaskMemFree(v9);
    *((_QWORD *)this + 27) = 0;
  }
  v10 = (void *)*((_QWORD *)this + 30);
  if ( v10 )
  {
    CoTaskMemFree(v10);
    *((_QWORD *)this + 30) = 0;
  }
  *((_QWORD *)this + 66) = 0;
  v11 = *((_QWORD *)this + 40) - *(_QWORD *)&GUID_NULL.Data1;
  if ( !v11 )
    v11 = *((_QWORD *)this + 41) - *(_QWORD *)GUID_NULL.Data4;
  if ( v11 )
    FreeBackupSetContents((CBlbRestoreFilesAsync *)((char *)this + 320));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
  }
}

```

## disassembly

```asm
0x140071174  mov     [rsp+arg_0], rbx
0x140071179  mov     [rsp+arg_8], rbp
0x14007117e  push    rdi
0x14007117f  sub     rsp, 20h
0x140071183  mov     rdi, rcx
0x140071186  lea     rbp, WPP_GLOBAL_Control
0x14007118d  mov     rcx, cs:WPP_GLOBAL_Control
0x140071194  cmp     rcx, rbp
0x140071197  jz      short loc_1400711BA
0x140071199  test    byte ptr [rcx+1Ch], 1
0x14007119d  jz      short loc_1400711BA
0x14007119f  cmp     byte ptr [rcx+19h], 4
0x1400711a3  jb      short loc_1400711BA
0x1400711a5  mov     edx, 0Ch
0x1400711aa  lea     r8, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids
0x1400711b1  mov     rcx, [rcx+10h]
0x1400711b5  call    WPP_SF_
0x1400711ba  mov     rcx, [rdi+0E0h]; void *
0x1400711c1  test    rcx, rcx
0x1400711c4  jz      short loc_1400711E7
0x1400711c6  lea     rbx, [rcx-8]
0x1400711ca  lea     r9, ??1CBlbRestoreFileContext@@QEAA@XZ; void (*)(void *)
0x1400711d1  mov     r8, [rbx]; unsigned __int64
0x1400711d4  mov     edx, 48h ; 'H'; unsigned __int64
0x1400711d9  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1400711de  mov     rcx, rbx; Block
0x1400711e1  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1400711e6  nop
0x1400711e7  mov     rcx, [rdi+110h]; pv
0x1400711ee  test    rcx, rcx
0x1400711f1  jz      short loc_140071204
0x1400711f3  call    cs:__imp_CoTaskMemFree
0x1400711f9  mov     qword ptr [rdi+110h], 0
0x140071204  mov     rcx, [rdi+118h]; pv
0x14007120b  test    rcx, rcx
0x14007120e  jz      short loc_140071221
0x140071210  call    cs:__imp_CoTaskMemFree
0x140071216  mov     qword ptr [rdi+118h], 0
0x140071221  mov     rcx, [rdi+120h]; pv
0x140071228  test    rcx, rcx
0x14007122b  jz      short loc_14007123E
0x14007122d  call    cs:__imp_CoTaskMemFree
0x140071233  mov     qword ptr [rdi+120h], 0
0x14007123e  mov     rcx, [rdi+128h]; pv
0x140071245  test    rcx, rcx
0x140071248  jz      short loc_14007125B
0x14007124a  call    cs:__imp_CoTaskMemFree
0x140071250  mov     qword ptr [rdi+128h], 0
0x14007125b  mov     rcx, [rdi+0D0h]; pv
0x140071262  test    rcx, rcx
0x140071265  jz      short loc_140071278
0x140071267  call    cs:__imp_CoTaskMemFree
0x14007126d  mov     qword ptr [rdi+0D0h], 0
0x140071278  mov     rcx, [rdi+0D8h]; pv
0x14007127f  test    rcx, rcx
0x140071282  jz      short loc_140071295
0x140071284  call    cs:__imp_CoTaskMemFree
0x14007128a  mov     qword ptr [rdi+0D8h], 0
0x140071295  mov     rcx, [rdi+0F0h]; pv
0x14007129c  test    rcx, rcx
0x14007129f  jz      short loc_1400712B2
0x1400712a1  call    cs:__imp_CoTaskMemFree
0x1400712a7  mov     qword ptr [rdi+0F0h], 0
0x1400712b2  mov     qword ptr [rdi+210h], 0
0x1400712bd  lea     rcx, [rdi+140h]; struct _BLBCAT_BACKUP_SET_INFO *
0x1400712c4  mov     rax, [rcx]
0x1400712c7  sub     rax, qword ptr cs:GUID_NULL.Data1
0x1400712ce  jnz     short loc_1400712DB
0x1400712d0  mov     rax, [rcx+8]
0x1400712d4  sub     rax, qword ptr cs:GUID_NULL.Data4
0x1400712db  test    rax, rax
0x1400712de  jz      short loc_1400712E5
0x1400712e0  call    ?FreeBackupSetContents@@YAXPEAU_BLBCAT_BACKUP_SET_INFO@@@Z; FreeBackupSetContents(_BLBCAT_BACKUP_SET_INFO *)
0x1400712e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400712ec  cmp     rcx, rbp
0x1400712ef  jz      short loc_140071312
0x1400712f1  test    byte ptr [rcx+1Ch], 1
0x1400712f5  jz      short loc_140071312
0x1400712f7  cmp     byte ptr [rcx+19h], 4
0x1400712fb  jb      short loc_140071312
0x1400712fd  mov     edx, 0Dh
0x140071302  lea     r8, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids
0x140071309  mov     rcx, [rcx+10h]
0x14007130d  call    WPP_SF_
0x140071312  mov     rbx, [rsp+28h+arg_0]
0x140071317  mov     rbp, [rsp+28h+arg_8]
0x14007131c  add     rsp, 20h
0x140071320  pop     rdi
0x140071321  retn
```
