# GetExtensionVersion

- ea: `0x180002070`
- end: `0x180002100`
- name: `GetExtensionVersion`
- size: `144`
- prototype: `BOOL __stdcall(HSE_VERSION_INFO *pVer)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180002070`
- `0x18000249c`

## string_xrefs

- `0x1800020b8`: `UPnP Device Host ISAPI Extension`

## pseudocode

```c
BOOL __stdcall GetExtensionVersion(HSE_VERSION_INFO *pVer)
{
  const char *v2; // r8
  CHAR *lpszExtensionDesc; // rbx
  __int64 v4; // rcx
  __int64 v5; // rdx
  CHAR *v6; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_fad536e1b3aa3094c8cccf7c139a598d_Traceguids);
  if ( pVer )
  {
    pVer->dwExtensionVersion = 1;
    v2 = "UPnP Device Host ISAPI Extension";
    lpszExtensionDesc = pVer->lpszExtensionDesc;
    v4 = 2147483646;
    v5 = 256;
    do
    {
      if ( !v4 )
        break;
      if ( !*v2 )
        break;
      *lpszExtensionDesc++ = *v2++;
      --v4;
      --v5;
    }
    while ( v5 );
    v6 = lpszExtensionDesc - 1;
    if ( v5 )
      v6 = lpszExtensionDesc;
    *v6 = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180002070  push    rbx
0x180002072  sub     rsp, 20h
0x180002076  mov     rbx, rcx
0x180002079  mov     rcx, cs:WPP_GLOBAL_Control
0x180002080  lea     rax, WPP_GLOBAL_Control
0x180002087  cmp     rcx, rax
0x18000208a  jz      short loc_1800020AA
0x18000208c  test    dword ptr [rcx+1Ch], 400h
0x180002093  jz      short loc_1800020AA
0x180002095  mov     rcx, [rcx+10h]
0x180002099  lea     r8, WPP_fad536e1b3aa3094c8cccf7c139a598d_Traceguids
0x1800020a0  mov     edx, 0Ch
0x1800020a5  call    WPP_SF_
0x1800020aa  mov     r9d, 1
0x1800020b0  test    rbx, rbx
0x1800020b3  jz      short loc_1800020F7
0x1800020b5  mov     [rbx], r9d
0x1800020b8  lea     r8, aUpnpDeviceHost; "UPnP Device Host ISAPI Extension"
0x1800020bf  add     rbx, 4
0x1800020c3  mov     ecx, 7FFFFFFEh
0x1800020c8  mov     edx, 100h
0x1800020cd  test    rcx, rcx
0x1800020d0  jz      short loc_1800020E9
0x1800020d2  mov     al, [r8]
0x1800020d5  test    al, al
0x1800020d7  jz      short loc_1800020E9
0x1800020d9  mov     [rbx], al
0x1800020db  add     r8, r9
0x1800020de  add     rbx, r9
0x1800020e1  sub     rcx, r9
0x1800020e4  sub     rdx, r9
0x1800020e7  jnz     short loc_1800020CD
0x1800020e9  test    rdx, rdx
0x1800020ec  lea     rcx, [rbx-1]
0x1800020f0  cmovnz  rcx, rbx
0x1800020f4  mov     byte ptr [rcx], 0
0x1800020f7  mov     eax, r9d
0x1800020fa  add     rsp, 20h
0x1800020fe  pop     rbx
0x1800020ff  retn
```
