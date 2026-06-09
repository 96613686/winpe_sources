# SkhalEfiInvokeRuntimeService

- ea: `0x1400884d4`
- end: `0x1400886f0`
- name: `SkhalEfiInvokeRuntimeService`
- size: `540`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x140014dd0`

## callees

- `0x1400119c4`
- `0x140012750`
- `0x1400202b0`
- `0x140050634`
- `0x1400884d4`
- `0x1400887e8`
- `0x1400888e8`
- `0x140088d80`
- `0x1400b5ac4`
- `0x1400f2fc0`

## pseudocode

```c
__int64 __fastcall SkhalEfiInvokeRuntimeService(int a1, __int64 a2, __int64 a3, _QWORD *a4, unsigned int *a5)
{
  unsigned __int64 v5; // rdi
  __int64 v6; // rbp
  __int64 v10; // r10
  ULONG_PTR v11; // r11
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // r14d
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  unsigned __int8 CurrentIrql; // r15
  int v19; // ebx
  int v20; // ebx
  int v21; // ebx
  int v22; // ebx
  int v23; // ebx
  __int64 *v24; // rbx
  __int64 v25; // rax
  __int64 NextVariableName; // rax
  __int64 v27; // rax
  __int64 v28[9]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v29; // [rsp+98h] [rbp+20h] BYREF

  v5 = 0x8000000000000003uLL;
  v6 = 0;
  *a4 = 0x8000000000000003uLL;
  if ( (SkhalpEfiFlags & 1) == 0 )
    return 0;
  if ( KeGetCurrentIrql() < 3u || !(unsigned __int8)SkTryAcquireSpinLockExclusiveAtDpcLevel() )
    SkeBugCheckEx(0x29u, 0x77466B53u, 0, 0, 0);
  if ( !v10 )
  {
    v15 = 0;
    v16 = 0;
    v17 = 0;
LABEL_9:
    CurrentIrql = KeGetCurrentIrql();
    __writecr8(0xFu);
    v14 = 0;
    if ( a1 )
    {
      v19 = a1 - 1;
      if ( v19 )
      {
        v20 = v19 - 1;
        if ( v20 )
        {
          v21 = v20 - 1;
          if ( v21 )
          {
            v22 = v21 - 1;
            if ( v22 )
            {
              v23 = v22 - 1;
              if ( v23 )
              {
                if ( v23 != 3 )
                {
                  v14 = -1073741822;
                  goto LABEL_33;
                }
                if ( qword_1401561A0 )
                {
                  v24 = (__int64 *)(a5 + 6);
                  v25 = qword_1401561A0(*a5, a5 + 2, a5 + 4, a5 + 6);
                  v15 = 2072008;
                  v5 = v25;
                  if ( (unsigned __int64)*v24 < 0x1F9DC8 )
                    v15 = *v24;
                  *v24 = v15;
                }
                goto LABEL_32;
              }
              NextVariableName = SkhalpEfiSetVariable(v15, v16, v17);
            }
            else
            {
              NextVariableName = SkhalpEfiGetNextVariableName(v15, v16, v17);
            }
          }
          else
          {
            NextVariableName = SkhalpEfiGetVariable(v15, v16, v17);
          }
          *a4 = NextVariableName;
          goto LABEL_33;
        }
        if ( qword_140156170 )
        {
          v27 = qword_140156170(*a5, *((_QWORD *)a5 + 1), 0, 0);
LABEL_31:
          v5 = v27;
        }
      }
      else if ( qword_140156168 )
      {
        v27 = qword_140156168(a5, v16, v17);
        goto LABEL_31;
      }
    }
    else if ( SkhalpEfiRuntimeServices )
    {
      v27 = SkhalpEfiRuntimeServices(a5, a5 + 4, v17);
      goto LABEL_31;
    }
LABEL_32:
    *a4 = v5;
LABEL_33:
    LOBYTE(v15) = CurrentIrql;
    SkeLowerIrql(v15);
    if ( v6 )
      SkmmUnmapDataTransfer(v6);
    goto LABEL_35;
  }
  v28[0] = SkhalpEfiMappingAddress;
  v29 = SkhalpEfiTransferMdl;
  *(_DWORD *)(SkhalpEfiTransferMdl + 40) = 2072576;
  v14 = SkmmMapDataTransfer(v10, v11, 0x202u, (ULONG_PTR *)&v29, v28);
  if ( v14 >= 0 )
  {
    v6 = v29;
    v15 = *(_QWORD *)(v29 + 24);
    v16 = *(unsigned int *)(v29 + 40);
    v17 = v15 - v28[0];
    goto LABEL_9;
  }
LABEL_35:
  SkhalpEfiServiceLock = 0;
  SkTrackSpinLockRelease(v13, v12);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1400884d4  push    rbx
0x1400884d6  push    rbp
0x1400884d7  push    rsi
0x1400884d8  push    rdi
0x1400884d9  push    r14
0x1400884db  push    r15
0x1400884dd  sub     rsp, 48h
0x1400884e1  mov     rdi, 8000000000000003h
0x1400884eb  xor     ebp, ebp
0x1400884ed  mov     [r9], rdi
0x1400884f0  mov     rsi, r9
0x1400884f3  mov     eax, cs:SkhalpEfiFlags
0x1400884f9  mov     r11, r8
0x1400884fc  mov     r10, rdx
0x1400884ff  mov     ebx, ecx
0x140088501  test    al, 1
0x140088503  jnz     short loc_140088515
0x140088505  xor     eax, eax
0x140088507  add     rsp, 48h
0x14008850b  pop     r15
0x14008850d  pop     r14
0x14008850f  pop     rdi
0x140088510  pop     rsi
0x140088511  pop     rbp
0x140088512  pop     rbx
0x140088513  retn
0x140088515  mov     rax, cr8
0x140088519  cmp     al, 3
0x14008851b  jb      loc_1400886D6
0x140088521  call    SkTryAcquireSpinLockExclusiveAtDpcLevel
0x140088526  test    al, al
0x140088528  jz      loc_1400886D6
0x14008852e  test    r10, r10
0x140088531  jz      short loc_14008859C
0x140088533  mov     rax, cs:SkhalpEfiMappingAddress
0x14008853a  lea     r9, [rsp+78h+arg_18]
0x140088542  mov     [rsp+78h+var_48], rax
0x140088547  mov     r8d, 202h
0x14008854d  mov     rax, cs:SkhalpEfiTransferMdl
0x140088554  mov     rdx, r11
0x140088557  mov     [rsp+78h+arg_18], rax
0x14008855f  mov     rcx, r10
0x140088562  mov     dword ptr [rax+28h], 1FA000h
0x140088569  lea     rax, [rsp+78h+var_48]
0x14008856e  mov     [rsp+78h+BugCheckParameter4], rax
0x140088573  call    SkmmMapDataTransfer
0x140088578  mov     r14d, eax
0x14008857b  test    eax, eax
0x14008857d  js      loc_1400886BF
0x140088583  mov     rbp, [rsp+78h+arg_18]
0x14008858b  mov     rcx, [rbp+18h]
0x14008858f  mov     edx, [rbp+28h]
0x140088592  mov     r8, rcx
0x140088595  sub     r8, [rsp+78h+var_48]
0x14008859a  jmp     short loc_1400885A3
0x14008859c  xor     ecx, ecx
0x14008859e  xor     edx, edx
0x1400885a0  xor     r8d, r8d
0x1400885a3  mov     r15, cr8
0x1400885a7  mov     eax, 0Fh
0x1400885ac  mov     cr8, rax
0x1400885b0  xor     r14d, r14d
0x1400885b3  test    ebx, ebx
0x1400885b5  jz      loc_140088687
0x1400885bb  sub     ebx, 1
0x1400885be  jz      loc_14008866C
0x1400885c4  sub     ebx, 1
0x1400885c7  jz      short loc_140088645
0x1400885c9  sub     ebx, 1
0x1400885cc  jz      short loc_14008863B
0x1400885ce  sub     ebx, 1
0x1400885d1  jz      short loc_140088634
0x1400885d3  sub     ebx, 1
0x1400885d6  jz      short loc_14008862D
0x1400885d8  cmp     ebx, 3
0x1400885db  jz      short loc_1400885E8
0x1400885dd  mov     r14d, 0C0000002h
0x1400885e3  jmp     loc_1400886AA
0x1400885e8  mov     rax, cs:qword_1401561A0
0x1400885ef  test    rax, rax
0x1400885f2  jz      loc_1400886A7
0x1400885f8  mov     rcx, [rsp+78h+arg_20]
0x140088600  lea     rbx, [rcx+18h]
0x140088604  lea     r8, [rcx+10h]
0x140088608  mov     r9, rbx
0x14008860b  lea     rdx, [rcx+8]
0x14008860f  mov     ecx, [rcx]
0x140088611  call    rax ; qword_1401561A0
0x140088613  nop     dword ptr [rax]
0x140088616  mov     ecx, 1F9DC8h
0x14008861b  mov     rdi, rax
0x14008861e  mov     rax, [rbx]
0x140088621  cmp     rax, rcx
0x140088624  cmovb   rcx, rax
0x140088628  mov     [rbx], rcx
0x14008862b  jmp     short loc_1400886A7
0x14008862d  call    SkhalpEfiSetVariable
0x140088632  jmp     short loc_140088640
0x140088634  call    SkhalpEfiGetNextVariableName
0x140088639  jmp     short loc_140088640
0x14008863b  call    SkhalpEfiGetVariable
0x140088640  mov     [rsi], rax
0x140088643  jmp     short loc_1400886AA
0x140088645  mov     rax, cs:qword_140156170
0x14008864c  test    rax, rax
0x14008864f  jz      short loc_1400886A7
0x140088651  mov     rcx, [rsp+78h+arg_20]
0x140088659  xor     r9d, r9d
0x14008865c  xor     r8d, r8d
0x14008865f  mov     rdx, [rcx+8]
0x140088663  mov     ecx, [rcx]
0x140088665  call    rax ; qword_140156170
0x140088667  nop     dword ptr [rax]
0x14008866a  jmp     short loc_1400886A4
0x14008866c  mov     rax, cs:qword_140156168
0x140088673  test    rax, rax
0x140088676  jz      short loc_1400886A7
0x140088678  mov     rcx, [rsp+78h+arg_20]
0x140088680  call    rax ; qword_140156168
0x140088682  nop     dword ptr [rax]
0x140088685  jmp     short loc_1400886A4
0x140088687  mov     rax, cs:SkhalpEfiRuntimeServices
0x14008868e  test    rax, rax
0x140088691  jz      short loc_1400886A7
0x140088693  mov     rcx, [rsp+78h+arg_20]
0x14008869b  lea     rdx, [rcx+10h]
0x14008869f  call    rax ; SkhalpEfiRuntimeServices
0x1400886a1  nop     dword ptr [rax]
0x1400886a4  mov     rdi, rax
0x1400886a7  mov     [rsi], rdi
0x1400886aa  mov     cl, r15b
0x1400886ad  call    SkeLowerIrql
0x1400886b2  test    rbp, rbp
0x1400886b5  jz      short loc_1400886BF
0x1400886b7  mov     rcx, rbp
0x1400886ba  call    SkmmUnmapDataTransfer
0x1400886bf  mov     cs:SkhalpEfiServiceLock, 0
0x1400886c9  call    SkTrackSpinLockRelease
0x1400886ce  mov     eax, r14d
0x1400886d1  jmp     loc_140088507
0x1400886d6  xor     r9d, r9d; BugCheckParameter3
0x1400886d9  mov     [rsp+78h+BugCheckParameter4], rbp; BugCheckParameter4
0x1400886de  xor     r8d, r8d; BugCheckParameter2
0x1400886e1  mov     edx, 77466B53h; BugCheckParameter1
0x1400886e6  lea     ecx, [r9+29h]; BugCheckCode
0x1400886ea  call    SkeBugCheckEx
```
