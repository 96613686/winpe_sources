# CmdLineParamProcessDashP(DkParameter &)

- ea: `0x100410730`
- end: `0x1004108e1`
- name: `?CmdLineParamProcessDashP@@YAXAEAVDkParameter@@@Z`
- size: `433`
- prototype: `void __fastcall(struct DkParameter *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x100401580`
- `0x100410730`

## import_xrefs

- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x10041074d`
- `sqldk!??0SystemAffinity@@QEAA@XZ` at `0x100410774`
- `sqldk!??0SystemAffinity@@QEAA@XZ` at `0x100410774`
- `sqldk!?SetAll@SystemAffinity@@QEAAXXZ` at `0x10041077f`
- `sqldk!?SetAll@SystemAffinity@@QEAAXXZ` at `0x10041077f`
- `sqldk!?GetCPUCount@SystemAffinity@@QEBAIXZ` at `0x100410793`
- `sqldk!?GetCPUCount@SystemAffinity@@QEBAIXZ` at `0x100410793`
- `sqldk!?GetGroupCount@SystemAffinity@@SAGXZ` at `0x1004107f0`
- `sqldk!?GetGroupCount@SystemAffinity@@SAGXZ` at `0x1004107f0`
- `sqldk!?SetNode@FakeOsNumaConfig@@QEAAXGG_K@Z` at `0x100410827`
- `sqldk!?SetNode@FakeOsNumaConfig@@QEAAXGG_K@Z` at `0x100410827`

## pseudocode

```c
void __fastcall CmdLineParamProcessDashP(struct DkParameter *a1)
{
  unsigned __int64 v2; // rdi
  unsigned __int16 v3; // si
  unsigned __int64 v4; // rbx
  _BYTE v5[128]; // [rsp+20h] [rbp-B8h] BYREF

  if ( *((_DWORD *)s_pServerConf + 2) == 2 )
  {
    v2 = *((unsigned int *)a1 + 6);
    SystemAffinity::SystemAffinity((SystemAffinity *)v5);
    SystemAffinity::SetAll((SystemAffinity *)v5);
    if ( v2 && v2 <= SystemAffinity::GetCPUCount((SystemAffinity *)v5) )
    {
      v3 = 0;
      do
      {
        if ( v3 >= (unsigned __int16)SystemAffinity::GetGroupCount() )
          break;
        v4 = -1;
        if ( v2 < 0x40 )
          v4 = (1LL << v2) - 1;
        FakeOsNumaConfig::SetNode((FakeOsNumaConfig *)&g_fakeOsNumaConfig, v3, v3, v4);
        ++v3;
        v2 -= (0x101010101010101LL
             * ((((v4 - ((v4 >> 1) & 0x5555555555555555LL)) & 0x3333333333333333LL)
               + (((v4 - ((v4 >> 1) & 0x5555555555555555LL)) >> 2) & 0x3333333333333333LL)
               + ((((v4 - ((v4 >> 1) & 0x5555555555555555LL)) & 0x3333333333333333LL)
                 + (((v4 - ((v4 >> 1) & 0x5555555555555555LL)) >> 2) & 0x3333333333333333LL)) >> 4))
              & 0xF0F0F0F0F0F0F0FLL)) >> 56;
      }
      while ( v2 );
      (*(void (__fastcall **)(__int64 *))(g_fakeOsNumaConfig + 112))(&g_fakeOsNumaConfig);
      *((_DWORD *)qword_10049F360 + 12127) |= 0x80u;
    }
    else
    {
      *((_DWORD *)a1 + 16) = 3;
      *((_QWORD *)a1 + 9) = 0;
    }
  }
}

```

## disassembly

```asm
0x100410730  mov     r11, rsp
0x100410733  push    rbx
0x100410734  sub     rsp, 0D0h
0x10041073b  mov     rax, cs:__security_cookie
0x100410742  xor     rax, rsp
0x100410745  mov     [rsp+0D8h+var_38], rax
0x10041074d  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x100410754  mov     rbx, rcx
0x100410757  mov     rdx, [rax]
0x10041075a  cmp     dword ptr [rdx+8], 2
0x10041075e  jnz     loc_1004108C8
0x100410764  mov     [r11+18h], rsi
0x100410768  mov     [r11-10h], rdi
0x10041076c  mov     edi, [rcx+18h]
0x10041076f  lea     rcx, [rsp+0D8h+var_B8]
0x100410774  call    cs:__imp_??0SystemAffinity@@QEAA@XZ; SystemAffinity::SystemAffinity(void)
0x10041077a  lea     rcx, [rsp+0D8h+var_B8]
0x10041077f  call    cs:__imp_?SetAll@SystemAffinity@@QEAAXXZ; SystemAffinity::SetAll(void)
0x100410785  test    rdi, rdi
0x100410788  jz      loc_1004108AB
0x10041078e  lea     rcx, [rsp+0D8h+var_B8]
0x100410793  call    cs:__imp_?GetCPUCount@SystemAffinity@@QEBAIXZ; SystemAffinity::GetCPUCount(void)
0x100410799  mov     eax, eax
0x10041079b  cmp     rdi, rax
0x10041079e  ja      loc_1004108AB
0x1004107a4  mov     [rsp+0D8h+arg_8], rbp
0x1004107ac  xor     esi, esi
0x1004107ae  mov     [rsp+0D8h+var_18], r12
0x1004107b6  mov     rbp, 3333333333333333h
0x1004107c0  mov     [rsp+0D8h+var_20], r14
0x1004107c8  mov     r12, 101010101010101h
0x1004107d2  mov     [rsp+0D8h+var_28], r15
0x1004107da  mov     r14, 5555555555555555h
0x1004107e4  mov     r15, 0F0F0F0F0F0F0F0Fh
0x1004107ee  xchg    ax, ax
0x1004107f0  call    cs:__imp_?GetGroupCount@SystemAffinity@@SAGXZ; SystemAffinity::GetGroupCount(void)
0x1004107f6  cmp     si, ax
0x1004107f9  jnb     short loc_100410866
0x1004107fb  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x100410802  cmp     rdi, 40h ; '@'
0x100410806  jnb     short loc_100410816
0x100410808  mov     rcx, rdi
0x10041080b  mov     ebx, 1
0x100410810  shl     rbx, cl
0x100410813  dec     rbx
0x100410816  mov     r9, rbx
0x100410819  lea     rcx, ?g_fakeOsNumaConfig@@3VSqlServerFakeOsNumaConfig@@A; SqlServerFakeOsNumaConfig g_fakeOsNumaConfig
0x100410820  movzx   r8d, si
0x100410824  movzx   edx, si
0x100410827  call    cs:__imp_?SetNode@FakeOsNumaConfig@@QEAAXGG_K@Z; FakeOsNumaConfig::SetNode(ushort,ushort,unsigned __int64)
0x10041082d  mov     rax, rbx
0x100410830  inc     si
0x100410833  shr     rax, 1
0x100410836  and     rax, r14
0x100410839  sub     rbx, rax
0x10041083c  mov     rcx, rbx
0x10041083f  and     rbx, rbp
0x100410842  shr     rcx, 2
0x100410846  and     rcx, rbp
0x100410849  add     rcx, rbx
0x10041084c  mov     rax, rcx
0x10041084f  shr     rax, 4
0x100410853  add     rax, rcx
0x100410856  and     rax, r15
0x100410859  imul    rax, r12
0x10041085d  shr     rax, 38h
0x100410861  sub     rdi, rax
0x100410864  jnz     short loc_1004107F0
0x100410866  mov     rax, cs:?g_fakeOsNumaConfig@@3VSqlServerFakeOsNumaConfig@@A; SqlServerFakeOsNumaConfig g_fakeOsNumaConfig
0x10041086d  lea     rcx, ?g_fakeOsNumaConfig@@3VSqlServerFakeOsNumaConfig@@A; SqlServerFakeOsNumaConfig g_fakeOsNumaConfig
0x100410874  call    qword ptr [rax+70h]
0x100410877  mov     rax, cs:qword_10049F360
0x10041087e  mov     r15, [rsp+0D8h+var_28]
0x100410886  mov     r14, [rsp+0D8h+var_20]
0x10041088e  mov     r12, [rsp+0D8h+var_18]
0x100410896  or      dword ptr [rax+0BD7Ch], 80h
0x1004108a0  mov     rbp, [rsp+0D8h+arg_8]
0x1004108a8  jmp     short loc_1004108B8
0x1004108ab  xor     esi, esi
0x1004108ad  mov     dword ptr [rbx+40h], 3
0x1004108b4  mov     [rbx+48h], rsi
0x1004108b8  mov     rsi, [rsp+0D8h+arg_10]
0x1004108c0  mov     rdi, [rsp+0D8h+var_10]
0x1004108c8  mov     rcx, [rsp+0D8h+var_38]
0x1004108d0  xor     rcx, rsp; StackCookie
0x1004108d3  call    __security_check_cookie
0x1004108d8  add     rsp, 0D0h
0x1004108df  pop     rbx
0x1004108e0  retn
```
