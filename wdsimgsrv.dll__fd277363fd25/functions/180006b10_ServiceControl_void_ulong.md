# ServiceControl(void *,ulong)

- ea: `0x180006b10`
- end: `0x180006be7`
- name: `?ServiceControl@@YAXPEAXK@Z`
- size: `215`
- prototype: `void __fastcall(struct _IMG_SERVER_CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x180006b10`
- `0x180009490`
- `0x18000b370`
- `0x18000c69c`

## string_xrefs

- `0x180006b24`: `-> ServiceControl`
- `0x180006bc7`: `<- ServiceControl=%x`
- `0x180006b70`: `\nRemote Install Path: [%s]\nImage Store Path: [%s]\nTimezone: [%s]\nOrgname [%s]`

## pseudocode

```c
void __fastcall ServiceControl(struct _IMG_SERVER_CONTEXT *a1, int a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  int v6; // r8d
  unsigned int refreshed; // eax
  CImageCache *v8; // rcx

  v4 = 0;
  WdsImgTrace(0x10000u, L"-> ServiceControl");
  switch ( a2 )
  {
    case 128:
      refreshed = pWdsImgSrvRefreshSettings(a1);
LABEL_11:
      v4 = refreshed;
      break;
    case 130:
      WdsImgTrace(0x10000u, L"-> pWdsImgSrvDumpState");
      if ( a1 )
        WdsImgTrace(
          0x20000u,
          L"\nRemote Install Path: [%s]\nImage Store Path: [%s]\nTimezone: [%s]\nOrgname [%s]",
          *(_QWORD *)a1,
          *((_QWORD *)a1 + 1),
          *((_QWORD *)a1 + 2),
          *((_QWORD *)a1 + 3));
      else
        v4 = 87;
      WdsImgTrace(0x10000u, L"<- pWdsImgSrvDumpState=%x", v4);
      break;
    case 131:
      v8 = (CImageCache *)*((_QWORD *)a1 + 12);
      if ( v8 )
      {
        refreshed = CImageCache::OnChange(v8, v5, v6);
        goto LABEL_11;
      }
      break;
  }
  WdsImgTrace(0x10000u, L"<- ServiceControl=%x", v4);
}

```

## disassembly

```asm
0x180006b10  mov     [rsp+arg_0], rbx
0x180006b15  mov     [rsp+arg_8], rsi
0x180006b1a  push    rdi
0x180006b1b  sub     rsp, 30h
0x180006b1f  mov     esi, edx
0x180006b21  mov     rdi, rcx
0x180006b24  lea     rdx, aServicecontrol_0; "-> ServiceControl"
0x180006b2b  mov     ecx, 10000h; unsigned int
0x180006b30  xor     ebx, ebx
0x180006b32  call    ?WdsImgTrace@@YAKKPEBGZZ; WdsImgTrace(ulong,ushort const *,...)
0x180006b37  cmp     esi, 80h
0x180006b3d  jnz     short loc_180006B49
0x180006b3f  mov     rcx, rdi; struct _IMG_SERVER_CONTEXT *
0x180006b42  call    ?pWdsImgSrvRefreshSettings@@YAKPEAU_IMG_SERVER_CONTEXT@@@Z; pWdsImgSrvRefreshSettings(_IMG_SERVER_CONTEXT *)
0x180006b47  jmp     short loc_180006BC2
0x180006b49  cmp     esi, 82h
0x180006b4f  jnz     short loc_180006BAC
0x180006b51  lea     rdx, aPwdsimgsrvdump_0; "-> pWdsImgSrvDumpState"
0x180006b58  mov     ecx, 10000h; unsigned int
0x180006b5d  call    ?WdsImgTrace@@YAKKPEBGZZ; WdsImgTrace(ulong,ushort const *,...)
0x180006b62  test    rdi, rdi
0x180006b65  jnz     short loc_180006B6C
0x180006b67  lea     ebx, [rsi-2Bh]
0x180006b6a  jmp     short loc_180006B96
0x180006b6c  mov     rax, [rdi+18h]
0x180006b70  lea     rdx, aRemoteInstallP; "\nRemote Install Path: [%s]\nImage Stor"...
0x180006b77  mov     r9, [rdi+8]
0x180006b7b  mov     ecx, 20000h; unsigned int
0x180006b80  mov     r8, [rdi]
0x180006b83  mov     [rsp+38h+var_10], rax
0x180006b88  mov     rax, [rdi+10h]
0x180006b8c  mov     [rsp+38h+var_18], rax
0x180006b91  call    ?WdsImgTrace@@YAKKPEBGZZ; WdsImgTrace(ulong,ushort const *,...)
0x180006b96  mov     r8d, ebx
0x180006b99  lea     rdx, aPwdsimgsrvdump; "<- pWdsImgSrvDumpState=%x"
0x180006ba0  mov     ecx, 10000h; unsigned int
0x180006ba5  call    ?WdsImgTrace@@YAKKPEBGZZ; WdsImgTrace(ulong,ushort const *,...)
0x180006baa  jmp     short loc_180006BC4
0x180006bac  cmp     esi, 83h
0x180006bb2  jnz     short loc_180006BC4
0x180006bb4  mov     rcx, [rdi+60h]; this
0x180006bb8  test    rcx, rcx
0x180006bbb  jz      short loc_180006BC4
0x180006bbd  call    ?OnChange@CImageCache@@QEAAKXZ; CImageCache::OnChange(void)
0x180006bc2  mov     ebx, eax
0x180006bc4  mov     r8d, ebx
0x180006bc7  lea     rdx, aServicecontrol; "<- ServiceControl=%x"
0x180006bce  mov     ecx, 10000h; unsigned int
0x180006bd3  mov     rbx, [rsp+38h+arg_0]
0x180006bd8  mov     rsi, [rsp+38h+arg_8]
0x180006bdd  add     rsp, 30h
0x180006be1  pop     rdi
0x180006be2  jmp     ?WdsImgTrace@@YAKKPEBGZZ; WdsImgTrace(ulong,ushort const *,...)
```
