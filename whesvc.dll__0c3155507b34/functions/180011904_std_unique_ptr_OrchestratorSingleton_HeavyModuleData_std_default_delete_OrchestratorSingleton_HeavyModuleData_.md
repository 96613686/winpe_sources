# std::unique_ptr<OrchestratorSingleton::HeavyModuleData,std::default_delete<OrchestratorSingleton::HeavyModuleData>>::~unique_ptr<OrchestratorSingleton::HeavyModuleData,std::default_delete<OrchestratorSingleton::HeavyModuleData>>(void)

- ea: `0x180011904`
- end: `0x18001197e`
- name: `??1?$unique_ptr@UHeavyModuleData@OrchestratorSingleton@@U?$default_delete@UHeavyModuleData@OrchestratorSingleton@@@std@@@std@@QEAA@XZ`
- size: `122`
- prototype: `void __fastcall(void **)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001164c`
- `0x180014398`
- `0x180014a14`
- `0x180014f94`
- `0x18002740b`

## callees

- `0x180003304`
- `0x180011578`
- `0x180011904`

## pseudocode

```c
void __fastcall std::unique_ptr<OrchestratorSingleton::HeavyModuleData>::~unique_ptr<OrchestratorSingleton::HeavyModuleData>(
        void **a1)
{
  char **v1; // rdi
  char *v2; // rbx
  unsigned __int64 v3; // rdx
  void *v4; // rcx

  v1 = (char **)*a1;
  if ( *a1 )
  {
    std::string::~string(v1 + 1);
    v2 = *v1;
    if ( *v1 )
    {
      std::string::~string((char **)v2 + 7);
      std::string::~string((char **)v2 + 3);
      v4 = (void *)*((_QWORD *)v2 + 1);
      if ( v4 )
        operator delete(v4, v3);
      if ( *(_QWORD *)v2 )
        operator delete(*(void **)v2, 0x18u);
      operator delete(v2, 0x58u);
    }
    operator delete(v1, 0x28u);
  }
}

```

## disassembly

```asm
0x180011904  mov     [rsp+arg_0], rbx
0x180011909  push    rdi
0x18001190a  sub     rsp, 20h
0x18001190e  mov     rdi, [rcx]
0x180011911  test    rdi, rdi
0x180011914  jz      short loc_180011973
0x180011916  lea     rcx, [rdi+8]
0x18001191a  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001191f  mov     rbx, [rdi]
0x180011922  test    rbx, rbx
0x180011925  jz      short loc_180011966
0x180011927  lea     rcx, [rbx+38h]
0x18001192b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180011930  lea     rcx, [rbx+18h]
0x180011934  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180011939  mov     rcx, [rbx+8]; void *
0x18001193d  test    rcx, rcx
0x180011940  jz      short loc_180011947
0x180011942  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011947  mov     rcx, [rbx]; void *
0x18001194a  test    rcx, rcx
0x18001194d  jz      short loc_180011959
0x18001194f  mov     edx, 18h; unsigned __int64
0x180011954  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011959  mov     edx, 58h ; 'X'; unsigned __int64
0x18001195e  mov     rcx, rbx; void *
0x180011961  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011966  mov     edx, 28h ; '('; unsigned __int64
0x18001196b  mov     rcx, rdi; void *
0x18001196e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011973  mov     rbx, [rsp+28h+arg_0]
0x180011978  add     rsp, 20h
0x18001197c  pop     rdi
0x18001197d  retn
```
