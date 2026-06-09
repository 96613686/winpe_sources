# CComputerNameSetting::get_Show(int *)

- ea: `0x180005ec0`
- end: `0x180005f16`
- name: `?get_Show@CComputerNameSetting@@UEAAJPEAH@Z`
- size: `86`
- prototype: `__int64 __fastcall(CComputerNameSetting *__hidden this, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180005360`
- `0x180005480`
- `0x180005ec0`
- `0x180006400`

## pseudocode

```c
__int64 __fastcall CComputerNameSetting::get_Show(CComputerNameSetting *this, int *a2)
{
  int v4; // ebx

  v4 = 0;
  if ( (unsigned int)CUpgradeUserSetting::IsUpgrade() )
    goto LABEL_4;
  if ( CUserSetting::ReadShow(this, a2, 0) < 0 )
  {
    v4 = 1;
LABEL_4:
    CUserSetting::set_Show(this, v4);
    *a2 = v4;
  }
  return 0;
}

```

## disassembly

```asm
0x180005ec0  mov     [rsp+arg_0], rbx
0x180005ec5  mov     [rsp+arg_8], rsi
0x180005eca  push    rdi
0x180005ecb  sub     rsp, 20h
0x180005ecf  mov     rdi, rdx
0x180005ed2  mov     rsi, rcx
0x180005ed5  xor     ebx, ebx
0x180005ed7  call    ?IsUpgrade@CUpgradeUserSetting@@SAHXZ; CUpgradeUserSetting::IsUpgrade(void)
0x180005edc  test    eax, eax
0x180005ede  jnz     short loc_180005EF7
0x180005ee0  xor     r8d, r8d; int
0x180005ee3  mov     rdx, rdi; int *
0x180005ee6  mov     rcx, rsi; this
0x180005ee9  call    ?ReadShow@CUserSetting@@IEAAJPEAHH@Z; CUserSetting::ReadShow(int *,int)
0x180005eee  test    eax, eax
0x180005ef0  jns     short loc_180005F03
0x180005ef2  mov     ebx, 1
0x180005ef7  mov     edx, ebx; int
0x180005ef9  mov     rcx, rsi; this
0x180005efc  call    ?set_Show@CUserSetting@@QEAAJH@Z; CUserSetting::set_Show(int)
0x180005f01  mov     [rdi], ebx
0x180005f03  mov     rbx, [rsp+28h+arg_0]
0x180005f08  xor     eax, eax
0x180005f0a  mov     rsi, [rsp+28h+arg_8]
0x180005f0f  add     rsp, 20h
0x180005f13  pop     rdi
0x180005f14  retn
```
