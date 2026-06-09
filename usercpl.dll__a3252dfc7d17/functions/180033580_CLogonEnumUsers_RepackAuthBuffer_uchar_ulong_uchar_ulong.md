# CLogonEnumUsers::_RepackAuthBuffer(uchar *,ulong,uchar * *,ulong *)

- ea: `0x180033580`
- end: `0x18003366b`
- name: `?_RepackAuthBuffer@CLogonEnumUsers@@AEAAJPEAEKPEAPEAEPEAK@Z`
- size: `235`
- prototype: `__int64 __fastcall(CLogonEnumUsers *this, char *, unsigned int, char **, unsigned int *AuthIdentityLength)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180030360`
- `0x1800304c0`

## callees

- `0x180033580`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800335b3`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x1800335b3`
- `SspiCli!SspiFreeAuthIdentity` at `0x180033649`
- `SspiCli!SspiFreeAuthIdentity` at `0x180033649`
- `SspiCli!SspiMarshalAuthIdentity` at `0x18003363c`
- `SspiCli!SspiMarshalAuthIdentity` at `0x18003363c`
- `SspiCli!SspiDecryptAuthIdentityEx` at `0x1800335fc`
- `SspiCli!SspiDecryptAuthIdentityEx` at `0x1800335fc`
- `SspiCli!SspiUnmarshalAuthIdentity` at `0x1800335cd`
- `SspiCli!SspiUnmarshalAuthIdentity` at `0x1800335cd`
- `SspiCli!SspiEncryptAuthIdentityEx` at `0x180033620`
- `SspiCli!SspiEncryptAuthIdentityEx` at `0x180033620`

## pseudocode

```c

```
