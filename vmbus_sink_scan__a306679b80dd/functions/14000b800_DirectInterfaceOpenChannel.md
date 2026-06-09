# DirectInterfaceOpenChannel

- ea: `0x14000b800`
- end: `0x14000b975`
- name: `DirectInterfaceOpenChannel`
- size: `373`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140002e20`
- `0x140002ed0`
- `0x140004974`
- `0x140004d50`
- `0x14000b800`
- `0x14000be98`
- `0x140010834`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14000b8b7`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000b8b7`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000b899`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000b899`

## pseudocode

```c
__int64 __fastcall DirectInterfaceOpenChannel(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rbx
  int v9; // r9d
  int v10; // edi
  __int64 v11; // rcx
  char v12; // al
  __int64 v13; // r8
  int v15; // [rsp+20h] [rbp-58h]
  __int64 v16; // [rsp+30h] [rbp-48h]
  unsigned int v17; // [rsp+30h] [rbp-48h]
  __int64 v18; // [rsp+38h] [rbp-40h]

  v5 = a1 + 8;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_b7e7155a638734823fba4b93e4cd9774_Traceguids);
  }
  InstanceWaitLockAcquire(v5, a2, a3);
  if ( *(_QWORD *)(v5 + 80) || *(_QWORD *)(v5 + 96) )
  {
    v10 = -2147483631;
  }
  else
  {
    v9 = *(_DWORD *)(v5 + 4);
    if ( v9 )
    {
      if ( (*(_DWORD *)(a2 + 124) & 1) != 0 )
      {
        ExAcquireFastMutex(&VmbusChannelTargetLock);
        InstancePdoUpdateTargetProcessor(v5, *(unsigned int *)(a2 + 120));
        ExReleaseFastMutex(&VmbusChannelTargetLock);
        v9 = *(_DWORD *)(v5 + 4);
      }
      v11 = *(_QWORD *)(v5 + 288);
      v12 = (*(_DWORD *)(a2 + 124) & 2) != 0;
      *(_QWORD *)(v5 + 96) = a3;
      v17 = *(_DWORD *)(v5 + 344);
      v15 = *(_DWORD *)(v5 + 56);
      *(_QWORD *)(v5 + 104) = a4;
      v10 = ChClientOpenChannel(v11, (__int64)DirectInterfaceOpenComplete, v5, v9, v15, (_OWORD *)a2, v17, v12);
      if ( v10 >= 0 )
      {
        v10 = 259;
      }
      else
      {
        *(_QWORD *)(v5 + 96) = 0;
        *(_QWORD *)(v5 + 80) = 0;
      }
    }
    else
    {
      v10 = -1073741661;
    }
  }
  InstanceWaitLockRelease(v5);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, 27, v13, a1, v5, v10, v16, v18);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14000b800  push    rbx
0x14000b802  push    rbp
0x14000b803  push    rsi
0x14000b804  push    rdi
0x14000b805  push    r12
0x14000b807  push    r14
0x14000b809  sub     rsp, 48h
0x14000b80d  mov     rbp, r9
0x14000b810  lea     rbx, [rcx+8]
0x14000b814  mov     r14, r8
0x14000b817  mov     rdi, rdx
0x14000b81a  mov     rsi, rcx
0x14000b81d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b824  lea     r12, WPP_GLOBAL_Control
0x14000b82b  cmp     rcx, r12
0x14000b82e  jz      short loc_14000B85A
0x14000b830  mov     eax, [rcx+2Ch]
0x14000b833  test    al, 10h
0x14000b835  jz      short loc_14000B85A
0x14000b837  cmp     byte ptr [rcx+29h], 4
0x14000b83b  jb      short loc_14000B85A
0x14000b83d  mov     rcx, [rcx+18h]
0x14000b841  lea     r8, WPP_b7e7155a638734823fba4b93e4cd9774_Traceguids
0x14000b848  mov     edx, 1Ah
0x14000b84d  mov     [rsp+78h+var_58], rbx
0x14000b852  mov     r9, rsi
0x14000b855  call    WPP_SF_qq
0x14000b85a  mov     rcx, rbx
0x14000b85d  call    InstanceWaitLockAcquire
0x14000b862  cmp     qword ptr [rbx+50h], 0
0x14000b867  jnz     loc_14000B925
0x14000b86d  cmp     qword ptr [rbx+60h], 0
0x14000b872  jnz     loc_14000B925
0x14000b878  mov     r9d, [rbx+4]
0x14000b87c  test    r9d, r9d
0x14000b87f  jnz     short loc_14000B88B
0x14000b881  mov     edi, 0C00000A3h
0x14000b886  jmp     loc_14000B92A
0x14000b88b  mov     eax, [rdi+7Ch]
0x14000b88e  test    al, 1
0x14000b890  jz      short loc_14000B8C7
0x14000b892  lea     rcx, VmbusChannelTargetLock; FastMutex
0x14000b899  call    cs:__imp_ExAcquireFastMutex
0x14000b8a0  nop     dword ptr [rax+rax+00h]
0x14000b8a5  mov     edx, [rdi+78h]
0x14000b8a8  mov     rcx, rbx
0x14000b8ab  call    InstancePdoUpdateTargetProcessor
0x14000b8b0  lea     rcx, VmbusChannelTargetLock; FastMutex
0x14000b8b7  call    cs:__imp_ExReleaseFastMutex
0x14000b8be  nop     dword ptr [rax+rax+00h]
0x14000b8c3  mov     r9d, [rbx+4]
0x14000b8c7  mov     eax, [rdi+7Ch]
0x14000b8ca  lea     rdx, DirectInterfaceOpenComplete
0x14000b8d1  mov     rcx, [rbx+120h]
0x14000b8d8  mov     r8, rbx
0x14000b8db  shr     eax, 1
0x14000b8dd  and     al, 1
0x14000b8df  mov     [rbx+60h], r14
0x14000b8e3  mov     byte ptr [rsp+78h+var_40], al
0x14000b8e7  mov     eax, [rbx+158h]
0x14000b8ed  mov     dword ptr [rsp+78h+var_48], eax
0x14000b8f1  mov     eax, [rbx+38h]
0x14000b8f4  mov     [rsp+78h+var_50], rdi
0x14000b8f9  mov     dword ptr [rsp+78h+var_58], eax
0x14000b8fd  mov     [rbx+68h], rbp
0x14000b901  call    ChClientOpenChannel
0x14000b906  mov     edi, eax
0x14000b908  test    eax, eax
0x14000b90a  jns     short loc_14000B91E
0x14000b90c  mov     qword ptr [rbx+60h], 0
0x14000b914  mov     qword ptr [rbx+50h], 0
0x14000b91c  jmp     short loc_14000B92A
0x14000b91e  mov     edi, 103h
0x14000b923  jmp     short loc_14000B92A
0x14000b925  mov     edi, 80000011h
0x14000b92a  mov     rcx, rbx
0x14000b92d  call    InstanceWaitLockRelease
0x14000b932  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b939  cmp     rcx, r12
0x14000b93c  jz      short loc_14000B965
0x14000b93e  mov     eax, [rcx+2Ch]
0x14000b941  test    al, 10h
0x14000b943  jz      short loc_14000B965
0x14000b945  cmp     byte ptr [rcx+29h], 4
0x14000b949  jb      short loc_14000B965
0x14000b94b  mov     rcx, [rcx+18h]
0x14000b94f  mov     edx, 1Bh
0x14000b954  mov     dword ptr [rsp+78h+var_50], edi
0x14000b958  mov     r9, rsi
0x14000b95b  mov     [rsp+78h+var_58], rbx
0x14000b960  call    WPP_SF_qqd
0x14000b965  mov     eax, edi
0x14000b967  add     rsp, 48h
0x14000b96b  pop     r14
0x14000b96d  pop     r12
0x14000b96f  pop     rdi
0x14000b970  pop     rsi
0x14000b971  pop     rbp
0x14000b972  pop     rbx
0x14000b973  retn
```
