# SP_ATTRIBUTES::Callback(_DEVICE_OBJECT *,_LIST_ENTRY *,_LIST_ENTRY *,void *)

- ea: `0x1400aab30`
- end: `0x1400aac72`
- name: `?Callback@SP_ATTRIBUTES@@CAJPEAU_DEVICE_OBJECT@@PEAU_LIST_ENTRY@@1PEAX@Z`
- size: `322`
- prototype: `static int(struct _DEVICE_OBJECT *, struct _LIST_ENTRY *, struct _LIST_ENTRY *, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x140021df0`
- `0x140034660`
- `0x140068110`
- `0x1400a2084`
- `0x1400a426c`
- `0x1400aab30`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1400aac46`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400aac46`
- `ntoskrnl!RtlStringFromGUID` at `0x1400aac0f`
- `ntoskrnl!RtlStringFromGUID` at `0x1400aac0f`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400aabb7`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400aabb7`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1400aab7e`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1400aab7e`

## pseudocode

```c
__int64 __fastcall SP_ATTRIBUTES::Callback(
        struct _DEVICE_OBJECT *a1,
        struct _LIST_ENTRY *a2,
        struct _LIST_ENTRY *a3,
        struct _ERESOURCE *a4)
{
  char v5; // bl
  __m256i *v6; // rax
  SP_CONTROL *DeviceExtension; // rbx
  PVOID RestartKey; // [rsp+30h] [rbp-19h] BYREF
  __int64 v10; // [rsp+38h] [rbp-11h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+40h] [rbp-9h] BYREF
  __m256i Guid; // [rsp+50h] [rbp+7h] BYREF

  memset(&Guid, 0, sizeof(Guid));
  while ( 2 )
  {
    v5 = 0;
    RestartKey = 0;
    SpAcquireResourceExclusive(a4 + 1);
    while ( 1 )
    {
      v6 = (__m256i *)RtlEnumerateGenericTableWithoutSplayingAvl((PRTL_AVL_TABLE)a4, &RestartKey);
      if ( !v6 )
        break;
      if ( v6->m256i_i32[6] )
      {
        Guid = *v6;
        v6->m256i_i32[6] = 0;
        if ( Guid.m256i_i32[6] == 2 )
          RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)a4, v6);
        v5 = 1;
        break;
      }
    }
    SpReleaseResourceExclusive(a4 + 1);
    if ( v5 )
    {
      if ( Guid.m256i_i32[6] == 1 )
      {
        DeviceExtension = (SP_CONTROL *)WPP_MAIN_CB.DeviceExtension;
        v10 = Guid.m256i_i64[2];
        GuidString = 0;
        if ( RtlStringFromGUID((const GUID *const)&Guid, &GuidString) >= 0 )
          SP_CONTROL::SetParameter(DeviceExtension, GuidString.Buffer, 0xBu, &v10, 8u, 0);
        RtlFreeUnicodeString(&GuidString);
      }
      else if ( Guid.m256i_i32[6] == 2 )
      {
        SP_CONTROL::DeleteParameter((SP_CONTROL *)1, (struct _GUID *)&Guid);
      }
      continue;
    }
    break;
  }
  return 0;
}

```

## disassembly

```asm
0x1400aab30  push    rbp
0x1400aab32  push    rbx
0x1400aab33  push    rsi
0x1400aab34  push    rdi
0x1400aab35  lea     rbp, [rsp-3Fh]
0x1400aab3a  sub     rsp, 88h
0x1400aab41  mov     rax, cs:__security_cookie
0x1400aab48  xor     rax, rsp
0x1400aab4b  mov     [rbp+57h+var_30], rax
0x1400aab4f  xorps   xmm0, xmm0
0x1400aab52  mov     [rbp+57h+Guid.Data1], 0
0x1400aab59  movups  xmmword ptr [rbp+57h+Guid.Data2], xmm0
0x1400aab5d  mov     rdi, r9
0x1400aab60  movups  [rbp+57h+var_40], xmm0
0x1400aab64  xor     bl, bl
0x1400aab66  mov     [rbp+57h+RestartKey], 0
0x1400aab6e  lea     rcx, [rdi+68h]; Resource
0x1400aab72  call    ?SpAcquireResourceExclusive@@YAXPEAU_ERESOURCE@@@Z; SpAcquireResourceExclusive(_ERESOURCE *)
0x1400aab77  lea     rdx, [rbp+57h+RestartKey]; RestartKey
0x1400aab7b  mov     rcx, rdi; Table
0x1400aab7e  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x1400aab85  nop     dword ptr [rax+rax+00h]
0x1400aab8a  test    rax, rax
0x1400aab8d  jz      short loc_1400AABC5
0x1400aab8f  cmp     dword ptr [rax+18h], 0
0x1400aab93  jz      short loc_1400AAB77
0x1400aab95  movups  xmm0, xmmword ptr [rax]
0x1400aab98  movups  xmmword ptr [rbp+57h+Guid.Data1], xmm0
0x1400aab9c  movups  xmm1, xmmword ptr [rax+10h]
0x1400aaba0  movups  [rbp+57h+var_40], xmm1
0x1400aaba4  mov     dword ptr [rax+18h], 0
0x1400aabab  cmp     dword ptr [rbp+57h+var_40+8], 2
0x1400aabaf  jnz     short loc_1400AABC3
0x1400aabb1  mov     rdx, rax; Buffer
0x1400aabb4  mov     rcx, rdi; Table
0x1400aabb7  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1400aabbe  nop     dword ptr [rax+rax+00h]
0x1400aabc3  mov     bl, 1
0x1400aabc5  lea     rcx, [rdi+68h]; Resource
0x1400aabc9  call    ?SpReleaseResourceExclusive@@YAXPEAU_ERESOURCE@@@Z; SpReleaseResourceExclusive(_ERESOURCE *)
0x1400aabce  test    bl, bl
0x1400aabd0  jz      loc_1400AAC57
0x1400aabd6  mov     ecx, dword ptr [rbp+57h+var_40+8]
0x1400aabd9  sub     ecx, 1; this
0x1400aabdc  jz      short loc_1400AABF1
0x1400aabde  cmp     ecx, 1
0x1400aabe1  jnz     short loc_1400AAB64
0x1400aabe3  lea     rdx, [rbp+57h+Guid]; struct _GUID *
0x1400aabe7  call    ?DeleteParameter@SP_CONTROL@@QEAAJPEAU_GUID@@@Z; SP_CONTROL::DeleteParameter(_GUID *)
0x1400aabec  jmp     loc_1400AAB64
0x1400aabf1  mov     rax, qword ptr [rbp+57h+var_40]
0x1400aabf5  lea     rdx, [rbp+57h+GuidString]; GuidString
0x1400aabf9  mov     rbx, cs:WPP_MAIN_CB.DeviceExtension
0x1400aac00  lea     rcx, [rbp+57h+Guid]; Guid
0x1400aac04  xorps   xmm0, xmm0
0x1400aac07  mov     [rbp+57h+var_68], rax
0x1400aac0b  movups  xmmword ptr [rbp+57h+GuidString.Length], xmm0
0x1400aac0f  call    cs:__imp_RtlStringFromGUID
0x1400aac16  nop     dword ptr [rax+rax+00h]
0x1400aac1b  test    eax, eax
0x1400aac1d  js      short loc_1400AAC42
0x1400aac1f  mov     rdx, [rbp+57h+GuidString.Buffer]; unsigned __int16 *
0x1400aac23  lea     r9, [rbp+57h+var_68]; void *
0x1400aac27  mov     [rsp+0A0h+var_78], 0; unsigned __int8
0x1400aac2c  mov     r8d, 0Bh; unsigned int
0x1400aac32  mov     rcx, rbx; this
0x1400aac35  mov     [rsp+0A0h+var_80], 8; unsigned int
0x1400aac3d  call    ?SetParameter@SP_CONTROL@@QEAAJPEAGKPEAXKE@Z; SP_CONTROL::SetParameter(ushort *,ulong,void *,ulong,uchar)
0x1400aac42  lea     rcx, [rbp+57h+GuidString]; UnicodeString
0x1400aac46  call    cs:__imp_RtlFreeUnicodeString
0x1400aac4d  nop     dword ptr [rax+rax+00h]
0x1400aac52  jmp     loc_1400AAB64
0x1400aac57  xor     eax, eax
0x1400aac59  mov     rcx, [rbp+57h+var_30]
0x1400aac5d  xor     rcx, rsp; StackCookie
0x1400aac60  call    __security_check_cookie
0x1400aac65  add     rsp, 88h
0x1400aac6c  pop     rdi
0x1400aac6d  pop     rsi
0x1400aac6e  pop     rbx
0x1400aac6f  pop     rbp
0x1400aac70  retn
```
