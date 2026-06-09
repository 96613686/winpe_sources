# WcQuerySecurity

- ea: `0x14001fa5c`
- end: `0x14001fc3f`
- name: `WcQuerySecurity`
- size: `483`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, SECURITY_INFORMATION SecurityInformation@<r8d>, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001d8dc`
- `0x14002da54`

## callees

- `0x1400020c4`
- `0x14001fa5c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001fc10`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fc10`
- `ntoskrnl!ExAllocatePool2` at `0x14001fb18`
- `ntoskrnl!ExAllocatePool2` at `0x14001fb18`
- `FLTMGR!FltQuerySecurityObject` at `0x14001fa92`
- `FLTMGR!FltQuerySecurityObject` at `0x14001fba6`
- `FLTMGR!FltQuerySecurityObject` at `0x14001fa92`
- `FLTMGR!FltQuerySecurityObject` at `0x14001fba6`

## pseudocode

```c
__int64 __fastcall WcQuerySecurity(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        SECURITY_INFORMATION SecurityInformation,
        _QWORD *a4,
        ULONG *a5)
{
  int v9; // edx
  NTSTATUS SecurityObject; // ebx
  void *Pool2; // rax
  int v12; // edx
  void *v13; // rdi
  int v14; // edx
  ULONG v15; // ecx
  ULONG LengthNeeded[18]; // [rsp+40h] [rbp-48h] BYREF

  LengthNeeded[0] = 0;
  SecurityObject = FltQuerySecurityObject(Instance, FileObject, SecurityInformation, 0, 0, LengthNeeded);
  if ( SecurityObject == -1073741789 )
  {
    Pool2 = (void *)ExAllocatePool2(256, LengthNeeded[0], 1936081751);
    v13 = Pool2;
    if ( Pool2 )
    {
      SecurityObject = FltQuerySecurityObject(
                         Instance,
                         FileObject,
                         SecurityInformation,
                         Pool2,
                         LengthNeeded[0],
                         LengthNeeded);
      if ( SecurityObject >= 0 )
      {
        v15 = LengthNeeded[0];
        *a4 = v13;
        *a5 = v15;
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v14) = 2;
          WPP_RECORDER_SF_sDd(
            WPP_GLOBAL_Control->DeviceExtension,
            v14,
            15,
            122,
            (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
            66,
            SecurityObject);
        }
        ExFreePoolWithTag(v13, 0x73664357u);
      }
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v12) = 2;
        WPP_RECORDER_SF_sDd(
          WPP_GLOBAL_Control->DeviceExtension,
          v12,
          15,
          121,
          (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
          51,
          LengthNeeded[0]);
      }
      return (unsigned int)-1073741801;
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_sDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        15,
        120,
        (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
        35,
        SecurityObject);
    }
    if ( !SecurityObject )
      return (unsigned int)-1073741823;
  }
  return (unsigned int)SecurityObject;
}

```

## disassembly

```asm
0x14001fa5c  push    rbx
0x14001fa5e  push    rbp
0x14001fa5f  push    rsi
0x14001fa60  push    rdi
0x14001fa61  push    r14
0x14001fa63  push    r15
0x14001fa65  sub     rsp, 58h
0x14001fa69  lea     rax, [rsp+88h+var_48]
0x14001fa6e  mov     [rsp+88h+var_48], 0
0x14001fa76  mov     rsi, r9
0x14001fa79  mov     [rsp+88h+LengthNeeded], rax; LengthNeeded
0x14001fa7e  xor     r9d, r9d; SecurityDescriptor
0x14001fa81  mov     [rsp+88h+Length], 0; Length
0x14001fa89  mov     ebp, r8d
0x14001fa8c  mov     r14, rdx
0x14001fa8f  mov     r15, rcx
0x14001fa92  call    cs:__imp_FltQuerySecurityObject
0x14001fa99  nop     dword ptr [rax+rax+00h]
0x14001fa9e  mov     ebx, eax
0x14001faa0  cmp     eax, 0C0000023h
0x14001faa5  jz      short loc_14001FB09
0x14001faa7  lea     rax, WPP_RECORDER_INITIALIZED
0x14001faae  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001fab5  jz      short loc_14001FAF7
0x14001fab7  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fabe  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14001fac5  mov     [rsp+88h+var_50], ebx
0x14001fac9  mov     r9d, 78h ; 'x'
0x14001facf  mov     [rsp+88h+var_58], 1023h
0x14001fad7  mov     dl, 2
0x14001fad9  mov     [rsp+88h+LengthNeeded], rax
0x14001fade  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14001fae5  mov     rcx, [rcx+40h]
0x14001fae9  lea     r8d, [r9-69h]
0x14001faed  mov     qword ptr [rsp+88h+Length], rax
0x14001faf2  call    WPP_RECORDER_SF_sDd
0x14001faf7  test    ebx, ebx
0x14001faf9  jnz     loc_14001FC2F
0x14001faff  mov     ebx, 0C0000001h
0x14001fb04  jmp     loc_14001FC2F
0x14001fb09  mov     edx, [rsp+88h+var_48]
0x14001fb0d  mov     ecx, 100h
0x14001fb12  mov     r8d, 73664357h
0x14001fb18  call    cs:__imp_ExAllocatePool2
0x14001fb1f  nop     dword ptr [rax+rax+00h]
0x14001fb24  mov     rdi, rax
0x14001fb27  test    rax, rax
0x14001fb2a  jnz     short loc_14001FB88
0x14001fb2c  lea     rax, WPP_RECORDER_INITIALIZED
0x14001fb33  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001fb3a  jz      short loc_14001FB7E
0x14001fb3c  mov     eax, [rsp+88h+var_48]
0x14001fb40  lea     r9d, [rdi+79h]
0x14001fb44  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fb4b  lea     r8d, [rdi+0Fh]
0x14001fb4f  mov     [rsp+88h+var_50], eax
0x14001fb53  mov     dl, 2
0x14001fb55  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14001fb5c  mov     [rsp+88h+var_58], 1033h
0x14001fb64  mov     [rsp+88h+LengthNeeded], rax
0x14001fb69  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14001fb70  mov     rcx, [rcx+40h]
0x14001fb74  mov     qword ptr [rsp+88h+Length], rax
0x14001fb79  call    WPP_RECORDER_SF_sDd
0x14001fb7e  mov     ebx, 0C0000017h
0x14001fb83  jmp     loc_14001FC2F
0x14001fb88  lea     rax, [rsp+88h+var_48]
0x14001fb8d  mov     r9, rdi; SecurityDescriptor
0x14001fb90  mov     [rsp+88h+LengthNeeded], rax; LengthNeeded
0x14001fb95  mov     r8d, ebp; SecurityInformation
0x14001fb98  mov     eax, [rsp+88h+var_48]
0x14001fb9c  mov     rdx, r14; FileObject
0x14001fb9f  mov     rcx, r15; Instance
0x14001fba2  mov     [rsp+88h+Length], eax; Length
0x14001fba6  call    cs:__imp_FltQuerySecurityObject
0x14001fbad  nop     dword ptr [rax+rax+00h]
0x14001fbb2  mov     ebx, eax
0x14001fbb4  test    eax, eax
0x14001fbb6  jns     short loc_14001FC1E
0x14001fbb8  lea     rax, WPP_RECORDER_INITIALIZED
0x14001fbbf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001fbc6  jz      short loc_14001FC08
0x14001fbc8  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fbcf  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14001fbd6  mov     [rsp+88h+var_50], ebx
0x14001fbda  mov     r9d, 7Ah ; 'z'
0x14001fbe0  mov     [rsp+88h+var_58], 1042h
0x14001fbe8  mov     dl, 2
0x14001fbea  mov     [rsp+88h+LengthNeeded], rax
0x14001fbef  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14001fbf6  mov     rcx, [rcx+40h]
0x14001fbfa  lea     r8d, [r9-6Bh]
0x14001fbfe  mov     qword ptr [rsp+88h+Length], rax
0x14001fc03  call    WPP_RECORDER_SF_sDd
0x14001fc08  mov     edx, 73664357h; Tag
0x14001fc0d  mov     rcx, rdi; P
0x14001fc10  call    cs:__imp_ExFreePoolWithTag
0x14001fc17  nop     dword ptr [rax+rax+00h]
0x14001fc1c  jmp     short loc_14001FC2F
0x14001fc1e  mov     rax, [rsp+88h+arg_20]
0x14001fc26  mov     ecx, [rsp+88h+var_48]
0x14001fc2a  mov     [rsi], rdi
0x14001fc2d  mov     [rax], ecx
0x14001fc2f  mov     eax, ebx
0x14001fc31  add     rsp, 58h
0x14001fc35  pop     r15
0x14001fc37  pop     r14
0x14001fc39  pop     rdi
0x14001fc3a  pop     rsi
0x14001fc3b  pop     rbp
0x14001fc3c  pop     rbx
0x14001fc3d  retn
```
