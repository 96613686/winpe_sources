# SecMgrLockAndCheckAdapterDeleted(MSMSEC_INTF_CONTEXT *)

- ea: `0x180011030`
- end: `0x180011209`
- name: `?SecMgrLockAndCheckAdapterDeleted@@YAKPEAUMSMSEC_INTF_CONTEXT@@@Z`
- size: `473`
- prototype: `unsigned int __fastcall(struct MSMSEC_INTF_CONTEXT *)`
- caller_count: `9`
- callee_count: `4`
- tags: ``

## callers

- `0x180003c78`
- `0x1800058b8`
- `0x180008e4c`
- `0x18001d72c`
- `0x1800428e0`
- `0x180056ea4`
- `0x180057390`
- `0x180058fc8`
- `0x180065fb0`

## callees

- `0x18000892c`
- `0x180008998`
- `0x180011030`
- `0x180055a38`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18001114f`
- `MobileNetworking!ReleaseWriteLock` at `0x18001114f`
- `MobileNetworking!AcquireWriteLock` at `0x180011099`
- `MobileNetworking!AcquireWriteLock` at `0x180011099`

## string_xrefs

- `0x180011088`: `SecMgrLockAndCheckAdapterDeleted`
- `0x18001113e`: `SecMgrLockAndCheckAdapterDeleted`

## pseudocode

```c
__int64 __fastcall SecMgrLockAndCheckAdapterDeleted(struct MSMSEC_INTF_CONTEXT *a1, __int64 a2, int a3)
{
  PVOID *v4; // rcx
  int v5; // r8d
  unsigned int v6; // edi
  PVOID *v8; // rcx

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 27, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 17) & 0x100) != 0 )
      WPP_SF_Ls((unsigned int)v4[7], 11, a3, *((_DWORD *)a1 + 624), (__int64)">>> Locking >>>");
    AcquireWriteLock(a1, (char *)a1 + 2512, "SecMgrLockAndCheckAdapterDeleted", 482);
    if ( *((_DWORD *)a1 + 654) )
    {
      v6 = 6;
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 29, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
          v8 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 17) & 0x100) != 0 )
          WPP_SF_Ls((unsigned int)v8[7], 11, v5, *((_DWORD *)a1 + 624), (__int64)"<<< Unlocking <<<");
      }
      ReleaseWriteLock(a1, (char *)a1 + 2512, "SecMgrLockAndCheckAdapterDeleted", 496);
    }
    else
    {
      v6 = 0;
    }
    goto LABEL_10;
  }
  v6 = 87;
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 68) & 1) != 0 )
  {
    WPP_SF_(v4[7], 28, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids);
LABEL_10:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 17) & 0x100) != 0 )
    WPP_SF_d(v4[7], 30, &WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x180011030  sub     rsp, 38h
0x180011034  mov     [rsp+38h+arg_0], rbx
0x180011039  mov     rbx, rcx
0x18001103c  mov     [rsp+38h+arg_8], rbp
0x180011041  mov     rcx, cs:WPP_GLOBAL_Control
0x180011048  lea     rbp, WPP_GLOBAL_Control
0x18001104f  cmp     rcx, rbp
0x180011052  jz      short loc_180011061
0x180011054  test    dword ptr [rcx+44h], 100h
0x18001105b  jnz     loc_180011160
0x180011061  mov     [rsp+38h+var_8], rdi
0x180011066  test    rbx, rbx
0x180011069  jz      short loc_1800110E5
0x18001106b  mov     [rsp+38h+arg_10], rsi
0x180011070  cmp     rcx, rbp
0x180011073  jz      short loc_180011082
0x180011075  test    dword ptr [rcx+44h], 100h
0x18001107c  jnz     loc_180011181
0x180011082  mov     r9d, 1E2h
0x180011088  lea     r8, aSecmgrlockandc; "SecMgrLockAndCheckAdapterDeleted"
0x18001108f  lea     rdx, [rbx+9D0h]
0x180011096  mov     rcx, rbx
0x180011099  call    cs:__imp_AcquireWriteLock
0x1800110a0  nop     dword ptr [rax+rax+00h]
0x1800110a5  cmp     dword ptr [rbx+0A38h], 0
0x1800110ac  jnz     loc_1800111A7
0x1800110b2  xor     edi, edi
0x1800110b4  mov     rsi, [rsp+38h+arg_10]
0x1800110b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800110c0  mov     rbx, [rsp+38h+arg_0]
0x1800110c5  cmp     rcx, rbp
0x1800110c8  mov     rbp, [rsp+38h+arg_8]
0x1800110cd  jz      short loc_1800110D8
0x1800110cf  test    dword ptr [rcx+44h], 100h
0x1800110d6  jnz     short loc_18001110C
0x1800110d8  mov     eax, edi
0x1800110da  mov     rdi, [rsp+38h+var_8]
0x1800110df  add     rsp, 38h
0x1800110e3  retn
0x1800110e5  mov     edi, 57h ; 'W'
0x1800110ea  cmp     rcx, rbp
0x1800110ed  jz      short loc_1800110C0
0x1800110ef  test    byte ptr [rcx+44h], 1
0x1800110f3  jz      short loc_1800110C0
0x1800110f5  mov     rcx, [rcx+38h]
0x1800110f9  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180011100  mov     edx, 1Ch
0x180011105  call    WPP_SF_
0x18001110a  jmp     short loc_1800110B9
0x18001110c  mov     rcx, [rcx+38h]
0x180011110  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x180011117  mov     edx, 1Eh
0x18001111c  mov     r9d, edi
0x18001111f  call    WPP_SF_d
0x180011124  jmp     short loc_1800110D8
0x180011126  cmp     rcx, rbp
0x180011129  jz      short loc_180011138
0x18001112b  test    dword ptr [rcx+44h], 100h
0x180011132  jnz     loc_1800111E3
0x180011138  mov     r9d, 1F0h
0x18001113e  lea     r8, aSecmgrlockandc; "SecMgrLockAndCheckAdapterDeleted"
0x180011145  lea     rdx, [rbx+9D0h]
0x18001114c  mov     rcx, rbx
0x18001114f  call    cs:__imp_ReleaseWriteLock
0x180011156  nop     dword ptr [rax+rax+00h]
0x18001115b  jmp     loc_1800110B4
0x180011160  mov     rcx, [rcx+38h]
0x180011164  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x18001116b  mov     edx, 1Bh
0x180011170  call    WPP_SF_
0x180011175  mov     rcx, cs:WPP_GLOBAL_Control
0x18001117c  jmp     loc_180011061
0x180011181  mov     r9d, [rbx+9C0h]
0x180011188  lea     rax, aLocking; ">>> Locking >>>"
0x18001118f  mov     rcx, [rcx+38h]
0x180011193  mov     edx, 0Bh
0x180011198  mov     [rsp+38h+var_18], rax
0x18001119d  call    WPP_SF_Ls
0x1800111a2  jmp     loc_180011082
0x1800111a7  mov     edi, 6
0x1800111ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800111b3  cmp     rcx, rbp
0x1800111b6  jz      short loc_180011138
0x1800111b8  test    byte ptr [rcx+44h], 1
0x1800111bc  jz      loc_180011126
0x1800111c2  mov     rcx, [rcx+38h]
0x1800111c6  lea     r8, WPP_ae01c481f8653c6245af2cd9b1c5a1a2_Traceguids
0x1800111cd  mov     edx, 1Dh
0x1800111d2  call    WPP_SF_
0x1800111d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800111de  jmp     loc_180011126
0x1800111e3  mov     r9d, [rbx+9C0h]
0x1800111ea  lea     rax, aUnlocking; "<<< Unlocking <<<"
0x1800111f1  mov     rcx, [rcx+38h]
0x1800111f5  mov     edx, 0Bh
0x1800111fa  mov     [rsp+38h+var_18], rax
0x1800111ff  call    WPP_SF_Ls
0x180011204  jmp     loc_180011138
```
