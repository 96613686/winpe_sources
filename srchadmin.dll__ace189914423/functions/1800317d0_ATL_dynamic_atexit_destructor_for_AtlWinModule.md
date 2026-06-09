# ATL::_dynamic_atexit_destructor_for___AtlWinModule__

- ea: `0x1800317d0`
- end: `0x180031885`
- name: `ATL::_dynamic_atexit_destructor_for___AtlWinModule__`
- size: `181`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003400`
- `0x180006834`
- `0x1800317d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031833`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031833`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003187e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003187e`
- `USER32!UnregisterClassA` at `0x180031810`
- `USER32!UnregisterClassA` at `0x180031810`

## pseudocode

```c
void ATL::_dynamic_atexit_destructor_for___AtlWinModule__()
{
  int v0; // ebx
  HINSTANCE i; // rdi

  if ( ATL::_AtlWinModule == 72 )
  {
    v0 = 0;
    for ( i = hInstance; v0 < (int)qword_1800418D0; ++v0 )
    {
      if ( v0 < 0 )
      {
        RaiseException(0xC000008C, 1u, 0, 0);
        JUMPOUT(0x180031884LL);
      }
      UnregisterClassA((LPCSTR)*((unsigned __int16 *)Block + v0), i);
    }
    ATL::CSimpleArray<unsigned short,ATL::CSimpleArrayEqualHelper<unsigned short>>::RemoveAll(&Block);
    DeleteCriticalSection(&stru_180041898);
    ATL::_AtlWinModule = 0;
  }
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  qword_1800418D0 = 0;
}

```

## disassembly

```asm
0x1800317d0  mov     [rsp+arg_0], rbx
0x1800317d5  mov     [rsp+arg_8], rsi
0x1800317da  push    rdi
0x1800317db  sub     rsp, 20h
0x1800317df  xor     esi, esi
0x1800317e1  cmp     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, 48h ; 'H'; ATL::CAtlWinModule ATL::_AtlWinModule
0x1800317e8  jnz     short loc_18003183F
0x1800317ea  cmp     dword ptr cs:qword_1800418D0, esi
0x1800317f0  mov     ebx, esi
0x1800317f2  mov     rdi, cs:hInstance
0x1800317f9  jle     short loc_180031820
0x1800317fb  test    ebx, ebx
0x1800317fd  js      short loc_18003186E
0x1800317ff  mov     rax, cs:Block
0x180031806  mov     rdx, rdi; hInstance
0x180031809  movsxd  rcx, ebx
0x18003180c  movzx   ecx, word ptr [rax+rcx*2]; lpClassName
0x180031810  call    cs:__imp_UnregisterClassA
0x180031816  inc     ebx
0x180031818  cmp     ebx, dword ptr cs:qword_1800418D0
0x18003181e  jl      short loc_1800317FB
0x180031820  lea     rcx, Block
0x180031827  call    ?RemoveAll@?$CSimpleArray@GV?$CSimpleArrayEqualHelper@G@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleArray<ushort,ATL::CSimpleArrayEqualHelper<ushort>>::RemoveAll(void)
0x18003182c  lea     rcx, stru_180041898; lpCriticalSection
0x180031833  call    cs:__imp_DeleteCriticalSection
0x180031839  mov     cs:?_AtlWinModule@ATL@@3VCAtlWinModule@1@A, esi; ATL::CAtlWinModule ATL::_AtlWinModule
0x18003183f  mov     rcx, cs:Block; Block
0x180031846  test    rcx, rcx
0x180031849  jz      short loc_180031857
0x18003184b  call    free
0x180031850  mov     cs:Block, rsi
0x180031857  mov     rbx, [rsp+28h+arg_0]
0x18003185c  mov     cs:qword_1800418D0, rsi
0x180031863  mov     rsi, [rsp+28h+arg_8]
0x180031868  add     rsp, 20h
0x18003186c  pop     rdi
0x18003186d  retn
0x18003186e  xor     r9d, r9d; lpArguments
0x180031871  xor     r8d, r8d; nNumberOfArguments
0x180031874  mov     edx, 1; dwExceptionFlags
0x180031879  mov     ecx, 0C000008Ch; dwExceptionCode
0x18003187e  call    cs:__imp_RaiseException
```
